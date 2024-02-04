# Set the gender for the fraction

       FACTION.models = {
	[1] = {
    "models/male2.mdl",
		"models/male2.mdl",
	},
	[2] = {
    "models/female2.mdl",
		"models/female2.mdl",
	},
       }

       function FACTION:GetModels(client, gender)
        return self.models[gender]
       end

       function FACTION:GenerateName(gender) -- As for the name, you can delete it if you wish.
        local isMale = gender == 1
        local firstname = GetHumanFirstNames(isMale)[isMale and math.random(1, HUMAN_NAMES_MALE) or math.random(1, HUMAN_NAMES_FEMALE)]
        local lastname = GetHumanLastNames()[math.random(1, HUMAN_LASTNAMES)]

        return firstname:sub(1, 1):upper() .. firstname:sub(2):lower() .. " " .. lastname:sub(1, 1):upper() .. lastname:sub(2):lower()
       end
