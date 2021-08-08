local module = {}

function module.Round(num, decimalPlace)
	local secondDecimalPlace = decimalPlace + 1
	
	local rep = false
	local alrRep = false
	local finalNum
	
	repeat
		local secondDecimalPlace = decimalPlace + 1


		local newNum = tostring(num)
		local splitNumber = string.split(newNum, '.')
		local roundingDigit = string.match(splitNumber[2], '%d?',decimalPlace)
		local digitUsedToRound = string.match(splitNumber[2], '%d?',secondDecimalPlace)
		
		
		if roundingDigit == false or roundingDigit == nil or roundingDigit == '' or roundingDigit == ' ' then
			warn('Theres no number in that decimal place...')
			return
		end
		
		if digitUsedToRound == false or digitUsedToRound == nil or digitUsedToRound == '' or digitUsedToRound == ' ' then
			digitUsedToRound = 0
		end
		
		if tonumber(digitUsedToRound) <= 4 then
			roundingDigit = tonumber(roundingDigit)
		elseif tonumber(digitUsedToRound) >= 5 then
			roundingDigit = tonumber(roundingDigit)
			roundingDigit += 1
		end

		if roundingDigit == 10 then
			if decimalPlace == 1 then
				finalNum = tonumber(splitNumber[1]) + 1
				rep = false
			elseif decimalPlace > 1 then
				local decimalFormat = '%.'..decimalPlace - 2 ..'s'
				local changingDigit = string.match(splitNumber[2], '%d?',decimalPlace - 1)
				local newDecPoint = string.format(decimalFormat, splitNumber[2])
				local addingFinal = changingDigit + 1
				if addingFinal == 10 then
					rep = true
					local decimalFormat = '%.'..decimalPlace - 2 ..'s'
					local newDecPoint = string.format(decimalFormat, splitNumber[2])
					finalNum = tonumber(splitNumber[1]..'.'..tostring(newDecPoint)..tostring(9))
				else
					local decimalFormat = '%.'..decimalPlace - 2 ..'s'
					local newDecPoint = string.format(decimalFormat, splitNumber[2])
					finalNum = tonumber(splitNumber[1]..'.'..tostring(newDecPoint)..tostring(changingDigit + 1))
					rep = false
				end
			end
		elseif roundingDigit < 10 then
			if decimalPlace - 1 > 0 then
				local decimalFormat = '%.'..decimalPlace - 1 ..'s'
				local newDecPoint = string.format(decimalFormat, splitNumber[2])
				finalNum = tonumber(splitNumber[1]..'.'..tostring(newDecPoint)..tostring(roundingDigit))
			else
				local decimalFormat = '%.'..0 ..'s'
				local newDecPoint = string.format(decimalFormat, splitNumber[2])
				print(newDecPoint)
				finalNum = tonumber(splitNumber[1]..'.'..tostring(newDecPoint)..tostring(roundingDigit))
			end
		end
		decimalPlace -= 1
		wait()
	until rep == false
	return finalNum
end


return module
