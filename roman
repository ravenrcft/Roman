def roman(userinput)
	number = userinput.to_s.scan /\d/
	enum = number.count
	output = []

	enum.times do |e|
		e += 1
		if e == 1
		# I = 1 || V = 5 || X = 10
			if number[enum - e].to_i <= 3
				output << "I" * number[enum - e].to_i
			elsif number[enum - e].to_i == 4
				output << "IV"
			elsif number[enum - e].to_i == 5
				output << "V"
			elsif number[enum - e].to_i >= 6 && number[enum - e].to_i <= 8
				output << "V" + "I" * (number[enum - e].to_i - 5)
			elsif number[enum - e].to_i == 9
				output << "IX"
			end
		elsif e == 2
		# X = 10 || L = 50 || C = 100
			if number[enum - e].to_i <= 3
				output << "X" * number[enum - e].to_i
			elsif number[enum - e].to_i == 4
				output << "XL"
			elsif number[enum - e].to_i == 5
				output << "L"
			elsif number[enum - e].to_i >= 6 && number[enum - e].to_i <= 8
				output << "L" + "X" * (number[enum - e].to_i - 5)
			elsif number[enum - e].to_i == 9
				output << "XC"
			end
		elsif e == 3
		# C = 100 || D = 500 || M = 1,000
			if number[enum - e].to_i <= 3
				output << "C" * number[enum - e].to_i
			elsif number[enum - e].to_i == 4
				output << "CD"
			elsif number[enum - e].to_i == 5
				output << "D"
			elsif number[enum - e].to_i >= 6 && number[enum - e].to_i <= 8
				output << "D" + "C" * (number[enum - e].to_i - 5)
			elsif number[enum - e].to_i == 9
				output << "CM"
			end
		elsif e >= 4
		# M = 1,000
			output << "M" * number[enum - e].to_i
		end	
	end
	return output.reverse.join("")
end

def reverseroman(userinput)
	roman = userinput.upcase.scan /\w/
	enum = roman.count
	output = 0

	enum.times do |e|
		if roman[e] == "I"
			output += 1	
		elsif roman[e] == "V"
			output += 5
			if roman[e - 1] == "I" && e - 1 >= 0
				output -= 2		
			end
		elsif roman[e] == "X"
			output += 10
			if roman[e - 1] == "I" && e - 1 >= 0
				output -= 2
			end
		elsif roman[e] == "L"
			output += 50
			if roman[e - 1] == "X" && e - 1 >= 0
				output -= 20
			end
		elsif roman[e] == "C"
			output += 100
			if roman[e - 1] == "X" && e - 1 >= 0
				output -= 20
			elsif roman[e - 1] == "L" && e - 1 >= 0
				output -= 100
			end
		elsif roman[e] == "D"
			output += 500
			if roman[e - 1] == "C" && e - 1 >= 0
				output -= 200
			end
		elsif roman[e] == "M"
			output += 1000
			if roman[e - 1] == "C" && e - 1 >= 0
				output -= 200
			elsif roman[e - 1] == "D" && e - 1 >= 0
				output -= 1000
			end			
		end
	end
	return output
end
