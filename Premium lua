local Rayfield = loadstring(game:HttpGet('https://sirius.menu/rayfield'))()

local CustomTheme = {
    TextColor = Color3.fromRGB(0, 0, 0),  -- Black text
    Background = Color3.fromRGB(255, 255, 255),  -- White background
    Topbar = Color3.fromRGB(255, 255, 255),  -- White topbar
    Shadow = Color3.fromRGB(200, 200, 200),  -- Light gray shadow
    NotificationBackground = Color3.fromRGB(255, 255, 255),
    NotificationActionsBackground = Color3.fromRGB(0, 0, 0),  -- Black notification actions
    TabBackground = Color3.fromRGB(255, 255, 255),  -- White tab background
    TabStroke = Color3.fromRGB(0, 0, 0),  -- Black tab stroke
    TabBackgroundSelected = Color3.fromRGB(230, 230, 230),  -- Light gray selected tab
    TabTextColor = Color3.fromRGB(0, 0, 0),  -- Black tab text
    SelectedTabTextColor = Color3.fromRGB(0, 0, 0),  -- Black selected tab text
    ElementBackground = Color3.fromRGB(255, 255, 255),  -- White element background
    ElementBackgroundHover = Color3.fromRGB(230, 230, 230),  -- Light gray hover
    SecondaryElementBackground = Color3.fromRGB(255, 255, 255),  -- White secondary background
    ElementStroke = Color3.fromRGB(0, 0, 0),  -- Black element stroke
    SecondaryElementStroke = Color3.fromRGB(0, 0, 0),  -- Black secondary stroke
    
    SliderBackground = Color3.fromRGB(255, 255, 255),  -- White slider background
    SliderProgress = Color3.fromRGB(0, 0, 0),  -- Black slider progress
    SliderStroke = Color3.fromRGB(0, 0, 0),  -- Black slider stroke
    ToggleBackground = Color3.fromRGB(255, 255, 255),  -- White toggle background
    ToggleEnabled = Color3.fromRGB(0, 0, 0),  -- Black when enabled
    ToggleDisabled = Color3.fromRGB(200, 200, 200),  -- Light gray when disabled
    ToggleEnabledStroke = Color3.fromRGB(0, 0, 0),  -- Black stroke when enabled
    ToggleDisabledStroke = Color3.fromRGB(200, 200, 200),  -- Light gray stroke when disabled
    ToggleEnabledOuterStroke = Color3.fromRGB(0, 0, 0),  -- Black outer stroke
    ToggleDisabledOuterStroke = Color3.fromRGB(200, 200, 200),  -- Light gray outer stroke
    DropdownSelected = Color3.fromRGB(0, 0, 0),  -- Black selected dropdown
    DropdownUnselected = Color3.fromRGB(255, 255, 255),  -- White unselected dropdown
    InputBackground = Color3.fromRGB(255, 255, 255),  -- White input background
    InputStroke = Color3.fromRGB(0, 0, 0),  -- Black input stroke
    PlaceholderColor = Color3.fromRGB(150, 150, 150)  -- Dark gray placeholder text
}

local Window = Rayfield:CreateWindow({
   Name = "Moon ┃ DOORS",
   Icon = "moon",
   LoadingTitle = "Loading Luckys UI HUB",
   LoadingSubtitle = "by Lucky and Feathered Kiwi",
   Theme = CustomTheme,
   DisableRayfieldPrompts = false,
   DisableBuildWarnings = false,
   ConfigurationSaving = {
      Enabled = true,
      FolderName = nil,
      FileName = "Big Hub"
   },
   Discord = {
      Enabled = false,
      Invite = "noinvitelink",
      RememberJoins = true
   },
   KeySystem = false,
   KeySettings = {
      Title = "Key System",
      Subtitle = "Key System",
      Note = "No method of obtaining the key is provided",
      FileName = "Key",
      SaveKey = true,
      GrabKeyFromSite = false,
      Key = {"LemmeJiggleEmBallz"}
   }
})

Rayfield:Notify({
   Title = "Welcome",
   Content = "Made by Lucky and Feathered Kiwi",
   Duration = 7.5,
   Image = "hand",
})

Rayfield:Notify({
   Title = "Info",
   Content = "Not all Scripts are mine",
   Duration = 7.5,
   Image = "arrow-big-up-dash",
})

Rayfield:Notify({
   Title = "!WARNING!",
   Content = "This file is protected by MoonSecV3 and Federal#9999",
   Duration = 6.5,
   Image = "ban",
})

local PlayerTab = Window:CreateTab("Player", 4483362458)
local PlayerSection = PlayerTab:CreateSection("Player")

 local Button = PlayerTab:CreateButton({
   Name = "Aproximate WalkSpeed",
   Callback = function()
   game.Players.LocalPlayer.Character.Humanoid.WalkSpeed = 22
   end,
})
 
 local Button = PlayerTab:CreateButton({
   Name = "MAX Field of View",
   Callback = function()
   workspace.CurrentCamera.FieldOfView = 120
   end,
})
 
local Slider = PlayerTab:CreateSlider({
    Name = "Walkspeed",
    Range = {16, 50},
    Increment = 2,
    Suffix = "Speed",
    CurrentValue = 0,
    Flag = "Walkspeed",
    Callback = function(Value)
        game.Players.LocalPlayer.Character.Humanoid.WalkSpeed = Value
    end,
})
 
local Slider = PlayerTab:CreateSlider({
    Name = "JumpPower",
    Range = {14, 50},
    Increment = 1,
    Suffix = "",
    CurrentValue = 0,
    Flag = "JumpPower",
    Callback = function(Value)
        game.Players.LocalPlayer.Character.Humanoid.JumpPower = Value
        print("JumpPower set to: " .. Value)
    end
})

-- Auto Interact Toggle
local Toggle = PlayerTab:CreateToggle({
    Name = "Auto Interact",
    CurrentValue = false,
    Flag = "autoInteract", 
    Callback = function(Value)
        if Value then
            spawn(function()
                while task.wait() do
                    for _, v in pairs(workspace.CurrentRooms:GetDescendants()) do
                        if (v.Name == "KeyObtain" or v.Name == "TimerLever" or 
                            (v.Name == "ActivateEventPrompt" and v:IsA("ProximityPrompt") and v.Parent.Parent.Name == "DrawerContainer") or
                            (v.Name == "LootPrompt" and v:IsA("ProximityPrompt") and v.Parent.Parent.Name == "DrawerContainer")) then
                            
                            if checkDistance(v:FindFirstChildWhichIsA("BasePart")) then
                                fireproximityprompt(v:FindFirstChild("ModulePrompt") or v:FindFirstChild("ActivateEventPrompt") or v)
                            end
                        end
                    end
                end
            end)
        end
    end
})

 local Toggle = PlayerTab:CreateToggle({
    Name = "Fullbright",
    CurrentValue = false,
    Flag = "FullbrightToggle", 
    Callback = function(Value)
        local lighting = game:GetService("Lighting")
        
        if Value then
            -- Store original lighting values
            _G.OriginalBrightness = lighting.Brightness
            _G.OriginalAmbient = lighting.Ambient
            _G.OriginalOutdoorAmbient = lighting.OutdoorAmbient
            _G.OriginalClockTime = lighting.ClockTime
            _G.OriginalFogEnd = lighting.FogEnd
            _G.OriginalFogStart = lighting.FogStart
            _G.OriginalGlobalShadows = lighting.GlobalShadows
            
            -- Enable fullbright
            lighting.Brightness = 2
            lighting.ClockTime = 14
            lighting.FogEnd = 100000
            lighting.FogStart = 0
            lighting.GlobalShadows = false
            lighting.Ambient = Color3.fromRGB(255, 255, 255)
            lighting.OutdoorAmbient = Color3.fromRGB(255, 255, 255)
            
            -- Remove all lighting effects
            for _, v in pairs(lighting:GetChildren()) do
                if v:IsA("BloomEffect") or v:IsA("SunRaysEffect") or v:IsA("ColorCorrectionEffect") or v:IsA("BlurEffect") then
                    _G.OriginalEffects = _G.OriginalEffects or {}
                    table.insert(_G.OriginalEffects, v:Clone())
                    v.Enabled = false
                end
            end
        else
            -- Restore original lighting values
            if _G.OriginalBrightness then
                lighting.Brightness = _G.OriginalBrightness
                lighting.Ambient = _G.OriginalAmbient
                lighting.OutdoorAmbient = _G.OriginalOutdoorAmbient
                lighting.ClockTime = _G.OriginalClockTime
                lighting.FogEnd = _G.OriginalFogEnd
                lighting.FogStart = _G.OriginalFogStart
                lighting.GlobalShadows = _G.OriginalGlobalShadows
            end
            
            -- Restore lighting effects
            if _G.OriginalEffects then
                for _, v in pairs(lighting:GetChildren()) do
                    if v:IsA("BloomEffect") or v:IsA("SunRaysEffect") or v:IsA("ColorCorrectionEffect") or v:IsA("BlurEffect") then
                        v.Enabled = true
                    end
                end
                _G.OriginalEffects = nil
            end
        end
    end,
})

-- Keep fullbright settings when lighting changes
game:GetService("Lighting").Changed:Connect(function()
    local currentToggleState = game:GetService("CoreGui"):WaitForChild("Rayfield"):GetValue("FullbrightToggle")
    if currentToggleState then
        game:GetService("Lighting").Brightness = 2
        game:GetService("Lighting").ClockTime = 14
        game:GetService("Lighting").FogEnd = 100000
        game:GetService("Lighting").FogStart = 0
        game:GetService("Lighting").GlobalShadows = false
        game:GetService("Lighting").Ambient = Color3.fromRGB(255, 255, 255)
        game:GetService("Lighting").OutdoorAmbient = Color3.fromRGB(255, 255, 255)
    end
end)
 
   local Button = PlayerTab:CreateButton({
   Name = "Guiding Light Trail",
   Callback = function()
  loadstring(game:HttpGet("https://pastebin.com/raw/WV2wZEuj"))()
   end,
}) 
 
     local Button = PlayerTab:CreateButton({
   Name = "Regenerate Health",
   Callback = function()
   game.Players.LocalPlayer.Character.Humanoid.Health = 100
   end,
})
 
    local Button = PlayerTab:CreateButton({
   Name = "Reset",
   Callback = function()
   game.Players.LocalPlayer.Character.Humanoid.Health = 0
   end,
})
 
   local Button = PlayerTab:CreateButton({
   Name = "Revive",
   Callback = function()
   Script.ReplicatedStorage.Revive:FireServer()
   end,
})

  local Button = PlayerTab:CreateButton({
   Name = "Play Again",
   Callback = function()
   Script.ReplicatedStorage.PlayAgain:FireServer()
   end,
})
 
   local Button = PlayerTab:CreateButton({
   Name = "Lobby",
   Callback = function()
   Script.ReplicatedStorage.Lobby:FireServer()
   end,
})

local ExploitsTab = Window:CreateTab("Exploits", "zap") -- Title, Image
local ExploitsSection = ExploitsTab:CreateSection("Exploits")

local Label = ExploitsTab:CreateLabel("Execute big seek in the room seek is going to spawn in.")


       local Button = ExploitsTab:CreateButton({
   Name = "Big Figure [Seek Chase]",
   Callback = function()
  -- SEEK

local ToFind = workspace:FindFirstChild("SeekMoving") or workspace:FindFirstChild("SeekMovingNewClone")

if ToFind then
	local SeekMoving = ToFind
	
	for _, Color in pairs(SeekMoving:GetDescendants()) do
		if Color:IsA("BasePart") or Color:IsA("Decal") then
			Color.Transparency = 1
		end
	end

	for _, Cheese in pairs(SeekMoving:GetDescendants()) do
		if Cheese:IsA("Beam") and Cheese.Name == "StringCheese" then
			Cheese:Destroy()
		end
	end

	task.wait()

	local Figure = game:GetObjects("rbxassetid://17147503424")[1]
	Figure.Body.Weld.C0 = CFrame.new(0, 0, 0) * CFrame.Angles(math.rad(0), math.rad(180), math.rad(0))
	Figure.Body.Weld.Part1 = SeekMoving.SeekRig.UpperTorso
	Figure.Parent = SeekMoving.SeekRig

	warn("SETUP SEEK")
end

   end,
})

       local Button = ExploitsTab:CreateButton({
   Name = "Big Seek [Library]",
   Callback = function()

-- FIGURE

function SetupFigure(Child)
	local Figure = Child:FindFirstChild("FigureSetup")

	if not Figure then
		return
	end

	Figure = Child.FigureSetup.FigureRig

	for _, v in pairs(Figure:GetDescendants()) do
		if v:IsA("BasePart") or v:IsA("Decal") then
			v.Transparency = 1
		end
	end

	task.wait()

	local Seek = game:GetObjects("rbxassetid://17147814210")[1]	
	Seek.Weld.Part1 = Figure.Torso
	Seek.Parent = Figure
end

workspace.CurrentRooms.ChildAdded:Connect(function(Child)
	task.wait(3)
	SetupFigure(Child)
end)

for _, Child in pairs(workspace.CurrentRooms:GetChildren()) do
	SetupFigure(Child)
end
   end,
})

local ModifiersTab = Window:CreateTab("Modifiers", 14380950090) -- Title, Image
local ModifiersSection = ModifiersTab:CreateSection("Modifiers")

local Label = ModifierTab:CreateLabel("Execute in Door 1")

local Button = ModifiersTab:CreateButton({
   Name = "Dark Mode",
   Callback = function()
   loadstring(game:HttpGet("https://raw.githubusercontent.com/RegularVynixu/Utilities/main/Doors/Dark%20Mode/source.lua"))()
   end,
})

local Button = ModifiersTab:CreateButton({
   Name = "Hardcore Mode",
   Callback = function()
   loadstring(game:HttpGet('https://raw.githubusercontent.com/plamen6789/HardcoreScriptDOORS/main/HardcoreModeScript'))()
   end,
})

local Button = ModifiersTab:CreateButton({
   Name = "Impossible Mode",
   Callback = function()
   loadstring(game:HttpGet("https://gist.githubusercontent.com/T0mix1608/ff0a607a510996f361c230a2de85f9e8/raw/7096f3796a8feb208b6c0b9029686150e878b7a1/gistfile1.txt", true))()
   end,
})

local Button = ModifiersTab:CreateButton({
   Name = "Birthday Mode",
   Callback = function()
   loadstring(game:HttpGet('https://raw.githubusercontent.com/plamen6789/BirthdayModeDOORS/main/BirthdayModeScript'))()
   end,
})

local Button = ModifiersTab:CreateButton({
   Name = "Chicken Mod",
   Callback = function()
   loadstring(game:HttpGet("https://raw.githubusercontent.com/iimateiYT/Scripts/main/Chicken%20Mod.lua", true))()
   end,
})

local Button = ModifiersTab:CreateButton({
   Name = "Rusty Hotel",
   Callback = function()
   loadstring(game:HttpGet("https://gist.githubusercontent.com/T0mix1608/ff0a607a510996f361c230a2de85f9e8/raw/7096f3796a8feb208b6c0b9029686150e878b7a1/gistfile1.txt", true))()
   end,
})

local BottlesTab = Window:CreateTab("Bottles", "milk") -- Title, Image
local BottlesSection = BottlesTab:CreateSection("Bottles")

local Label = BottlesTab:CreateLabel("Open Door 1 and Press Q on your keyboard")

   local Button = BottlesTab:CreateButton({
   Name = "Herb Bottle of Light",
   Callback = function()
   local GuidingLight = "herb"
local GuidingLights = {
	["herb"] = {
		Color = Color3.fromRGB(0, 125, 0),
		Icon = "http://www.roblox.com/asset/?id=128170076314731"
	},
	["modifier"] = {
		Color = Color3.fromRGB(229, 118, 114),
		Icon = "rbxassetid://14380950090"
	},
	["revive"] = {
		Color = Color3.fromRGB(224, 92, 98),
		Icon = "rbxassetid://16587986504"
	},
	["gold"] = {
		Color = Color3.fromRGB(249, 237, 159),
		Icon = "rbxassetid://16587947721"
	},
	["knob"] = {
		Color = Color3.fromRGB(232, 143, 138),
		Icon = "rbxassetid://16587915599"
	},
	["knob boost"] = {
		Color = Color3.fromRGB(241, 155, 60),
		Icon = "rbxassetid://10448639430"
	}
}

local KillBottleKey = Enum.KeyCode.Q
local CustomDeathMessages = {
	"yo",
	"lemme jiggle em' balls - lsplash"
}

-----------------------------------------------------------------------

GuidingLight = string.lower(GuidingLight)

local ReplicatedStorage = game:GetService("ReplicatedStorage")
local Players = game:GetService("Players")

local Cache = game:GetObjects("rbxassetid://78559391457970")[1]
Cache:Destroy()

function setupLight(Child, Color, Icon)
	for _, Thing in pairs(Child:GetDescendants()) do
		if Thing:IsA("ParticleEmitter") then
			Thing.Color = ColorSequence.new(Color)
		elseif Thing:IsA("SpotLight") then
			Thing.Color = Color
		end
	end

	Players.LocalPlayer.PlayerGui.MainUI.Death.HelpfulDialogue.TextColor3 = Color

	Child.Lights.BigLight.Attachment.Moon.Color = ColorSequence.new(Color)
	Child.Lights.BigLight.Attachment.Moon.Texture = Icon
end

local MainGuidingLight = GuidingLights[GuidingLight]
if not MainGuidingLight then
	warn("This Light Does Not Exist!")
	return
end

workspace.CurrentCamera.ChildAdded:Connect(function(Child)
	if string.find(string.lower(Child.Name), "deathbackground") then
		setupLight(Child, MainGuidingLight.Color, MainGuidingLight.Icon)
	end
end)

game:GetService("UserInputService").InputBegan:Connect(function(input, gP)
	if input.KeyCode == KillBottleKey and not gP then
		local StarVile = game:GetObjects("rbxassetid://78559391457970")[1]
		StarVile.Parent = workspace.CurrentRooms[ReplicatedStorage.GameData.LatestRoom.Value]

		StarVile:PivotTo(Players.LocalPlayer.Character.HumanoidRootPart.CFrame)

		StarVile.Union.Color = MainGuidingLight.Color
		StarVile.Union2.Color = MainGuidingLight.Color
		StarVile.ModulePrompt.Triggered:Connect(function()
			if ReplicatedStorage.GameData.LatestRoom.Value >= 1 then
				firesignal(ReplicatedStorage.RemotesFolder.DeathHint.OnClientEvent, CustomDeathMessages, "Blue")
				task.wait(0.5)
				Players.LocalPlayer.Character.Humanoid.Health = 0
			end
		end)
	end
end)

   end,
})

   local Button = BottlesTab:CreateButton({
   Name = "Modifier Bottle of Light",
   Callback = function()
   local GuidingLight = "modifier"
local GuidingLights = {
	["herb"] = {
		Color = Color3.fromRGB(0, 125, 0),
		Icon = "http://www.roblox.com/asset/?id=128170076314731"
	},
	["modifier"] = {
		Color = Color3.fromRGB(229, 118, 114),
		Icon = "rbxassetid://14380950090"
	},
	["revive"] = {
		Color = Color3.fromRGB(224, 92, 98),
		Icon = "rbxassetid://16587986504"
	},
	["gold"] = {
		Color = Color3.fromRGB(249, 237, 159),
		Icon = "rbxassetid://16587947721"
	},
	["knob"] = {
		Color = Color3.fromRGB(232, 143, 138),
		Icon = "rbxassetid://16587915599"
	},
	["knob boost"] = {
		Color = Color3.fromRGB(241, 155, 60),
		Icon = "rbxassetid://10448639430"
	}
}

local KillBottleKey = Enum.KeyCode.Q
local CustomDeathMessages = {
	"Bruv",
	"should i make jiggle kardins ballz modifier?"
}

-----------------------------------------------------------------------

GuidingLight = string.lower(GuidingLight)

local ReplicatedStorage = game:GetService("ReplicatedStorage")
local Players = game:GetService("Players")

local Cache = game:GetObjects("rbxassetid://78559391457970")[1]
Cache:Destroy()

function setupLight(Child, Color, Icon)
	for _, Thing in pairs(Child:GetDescendants()) do
		if Thing:IsA("ParticleEmitter") then
			Thing.Color = ColorSequence.new(Color)
		elseif Thing:IsA("SpotLight") then
			Thing.Color = Color
		end
	end

	Players.LocalPlayer.PlayerGui.MainUI.Death.HelpfulDialogue.TextColor3 = Color

	Child.Lights.BigLight.Attachment.Moon.Color = ColorSequence.new(Color)
	Child.Lights.BigLight.Attachment.Moon.Texture = Icon
end

local MainGuidingLight = GuidingLights[GuidingLight]
if not MainGuidingLight then
	warn("This Light Does Not Exist!")
	return
end

workspace.CurrentCamera.ChildAdded:Connect(function(Child)
	if string.find(string.lower(Child.Name), "deathbackground") then
		setupLight(Child, MainGuidingLight.Color, MainGuidingLight.Icon)
	end
end)

game:GetService("UserInputService").InputBegan:Connect(function(input, gP)
	if input.KeyCode == KillBottleKey and not gP then
		local StarVile = game:GetObjects("rbxassetid://78559391457970")[1]
		StarVile.Parent = workspace.CurrentRooms[ReplicatedStorage.GameData.LatestRoom.Value]

		StarVile:PivotTo(Players.LocalPlayer.Character.HumanoidRootPart.CFrame)

		StarVile.Union.Color = MainGuidingLight.Color
		StarVile.Union2.Color = MainGuidingLight.Color
		StarVile.ModulePrompt.Triggered:Connect(function()
			if ReplicatedStorage.GameData.LatestRoom.Value >= 1 then
				firesignal(ReplicatedStorage.RemotesFolder.DeathHint.OnClientEvent, CustomDeathMessages, "Blue")
				task.wait(0.5)
				Players.LocalPlayer.Character.Humanoid.Health = 0
			end
		end)
	end
end)

   end,
})

   local Button = BottlesTab:CreateButton({
   Name = "Revive Bottle of Light",
   Callback = function()
   local GuidingLight = "revive"
local GuidingLights = {
	["herb"] = {
		Color = Color3.fromRGB(0, 125, 0),
		Icon = "http://www.roblox.com/asset/?id=128170076314731"
	},
	["modifier"] = {
		Color = Color3.fromRGB(229, 118, 114),
		Icon = "rbxassetid://14380950090"
	},
	["revive"] = {
		Color = Color3.fromRGB(224, 92, 98),
		Icon = "rbxassetid://16587986504"
	},
	["gold"] = {
		Color = Color3.fromRGB(249, 237, 159),
		Icon = "rbxassetid://16587947721"
	},
	["knob"] = {
		Color = Color3.fromRGB(232, 143, 138),
		Icon = "rbxassetid://16587915599"
	},
	["knob boost"] = {
		Color = Color3.fromRGB(241, 155, 60),
		Icon = "rbxassetid://10448639430"
	}
}

local KillBottleKey = Enum.KeyCode.Q
local CustomDeathMessages = {
	"Hello",
	"Im revive, Balls?"
}

-----------------------------------------------------------------------

GuidingLight = string.lower(GuidingLight)

local ReplicatedStorage = game:GetService("ReplicatedStorage")
local Players = game:GetService("Players")

local Cache = game:GetObjects("rbxassetid://78559391457970")[1]
Cache:Destroy()

function setupLight(Child, Color, Icon)
	for _, Thing in pairs(Child:GetDescendants()) do
		if Thing:IsA("ParticleEmitter") then
			Thing.Color = ColorSequence.new(Color)
		elseif Thing:IsA("SpotLight") then
			Thing.Color = Color
		end
	end

	Players.LocalPlayer.PlayerGui.MainUI.Death.HelpfulDialogue.TextColor3 = Color

	Child.Lights.BigLight.Attachment.Moon.Color = ColorSequence.new(Color)
	Child.Lights.BigLight.Attachment.Moon.Texture = Icon
end

local MainGuidingLight = GuidingLights[GuidingLight]
if not MainGuidingLight then
	warn("This Light Does Not Exist!")
	return
end

workspace.CurrentCamera.ChildAdded:Connect(function(Child)
	if string.find(string.lower(Child.Name), "deathbackground") then
		setupLight(Child, MainGuidingLight.Color, MainGuidingLight.Icon)
	end
end)

game:GetService("UserInputService").InputBegan:Connect(function(input, gP)
	if input.KeyCode == KillBottleKey and not gP then
		local StarVile = game:GetObjects("rbxassetid://78559391457970")[1]
		StarVile.Parent = workspace.CurrentRooms[ReplicatedStorage.GameData.LatestRoom.Value]

		StarVile:PivotTo(Players.LocalPlayer.Character.HumanoidRootPart.CFrame)

		StarVile.Union.Color = MainGuidingLight.Color
		StarVile.Union2.Color = MainGuidingLight.Color
		StarVile.ModulePrompt.Triggered:Connect(function()
			if ReplicatedStorage.GameData.LatestRoom.Value >= 1 then
				firesignal(ReplicatedStorage.RemotesFolder.DeathHint.OnClientEvent, CustomDeathMessages, "Blue")
				task.wait(0.5)
				Players.LocalPlayer.Character.Humanoid.Health = 0
			end
		end)
	end
end)

   end,
})

   local Button = BottlesTab:CreateButton({
   Name = "Gold Bottle of Light",
   Callback = function()
   local GuidingLight = "gold"
local GuidingLights = {
	["herb"] = {
		Color = Color3.fromRGB(0, 125, 0),
		Icon = "http://www.roblox.com/asset/?id=128170076314731"
	},
	["modifier"] = {
		Color = Color3.fromRGB(229, 118, 114),
		Icon = "rbxassetid://14380950090"
	},
	["revive"] = {
		Color = Color3.fromRGB(224, 92, 98),
		Icon = "rbxassetid://16587986504"
	},
	["gold"] = {
		Color = Color3.fromRGB(249, 237, 159),
		Icon = "rbxassetid://16587947721"
	},
	["knob"] = {
		Color = Color3.fromRGB(232, 143, 138),
		Icon = "rbxassetid://16587915599"
	},
	["knob boost"] = {
		Color = Color3.fromRGB(241, 155, 60),
		Icon = "rbxassetid://10448639430"
	}
}

local KillBottleKey = Enum.KeyCode.Q
local CustomDeathMessages = {
	"wsp",
	"Im Gold aka jiggle balls master"
}

-----------------------------------------------------------------------

GuidingLight = string.lower(GuidingLight)

local ReplicatedStorage = game:GetService("ReplicatedStorage")
local Players = game:GetService("Players")

local Cache = game:GetObjects("rbxassetid://78559391457970")[1]
Cache:Destroy()

function setupLight(Child, Color, Icon)
	for _, Thing in pairs(Child:GetDescendants()) do
		if Thing:IsA("ParticleEmitter") then
			Thing.Color = ColorSequence.new(Color)
		elseif Thing:IsA("SpotLight") then
			Thing.Color = Color
		end
	end

	Players.LocalPlayer.PlayerGui.MainUI.Death.HelpfulDialogue.TextColor3 = Color

	Child.Lights.BigLight.Attachment.Moon.Color = ColorSequence.new(Color)
	Child.Lights.BigLight.Attachment.Moon.Texture = Icon
end

local MainGuidingLight = GuidingLights[GuidingLight]
if not MainGuidingLight then
	warn("This Light Does Not Exist!")
	return
end

workspace.CurrentCamera.ChildAdded:Connect(function(Child)
	if string.find(string.lower(Child.Name), "deathbackground") then
		setupLight(Child, MainGuidingLight.Color, MainGuidingLight.Icon)
	end
end)

game:GetService("UserInputService").InputBegan:Connect(function(input, gP)
	if input.KeyCode == KillBottleKey and not gP then
		local StarVile = game:GetObjects("rbxassetid://78559391457970")[1]
		StarVile.Parent = workspace.CurrentRooms[ReplicatedStorage.GameData.LatestRoom.Value]

		StarVile:PivotTo(Players.LocalPlayer.Character.HumanoidRootPart.CFrame)

		StarVile.Union.Color = MainGuidingLight.Color
		StarVile.Union2.Color = MainGuidingLight.Color
		StarVile.ModulePrompt.Triggered:Connect(function()
			if ReplicatedStorage.GameData.LatestRoom.Value >= 1 then
				firesignal(ReplicatedStorage.RemotesFolder.DeathHint.OnClientEvent, CustomDeathMessages, "Blue")
				task.wait(0.5)
				Players.LocalPlayer.Character.Humanoid.Health = 0
			end
		end)
	end
end)

   end,
})

   local Button = BottlesTab:CreateButton({
   Name = "Knob Bottle of Light",
   Callback = function()
   local GuidingLight = "knob"
local GuidingLights = {
	["herb"] = {
		Color = Color3.fromRGB(0, 125, 0),
		Icon = "http://www.roblox.com/asset/?id=128170076314731"
	},
	["modifier"] = {
		Color = Color3.fromRGB(229, 118, 114),
		Icon = "rbxassetid://14380950090"
	},
	["revive"] = {
		Color = Color3.fromRGB(224, 92, 98),
		Icon = "rbxassetid://16587986504"
	},
	["gold"] = {
		Color = Color3.fromRGB(249, 237, 159),
		Icon = "rbxassetid://16587947721"
	},
	["knob"] = {
		Color = Color3.fromRGB(232, 143, 138),
		Icon = "rbxassetid://16587915599"
	},
	["knob boost"] = {
		Color = Color3.fromRGB(241, 155, 60),
		Icon = "rbxassetid://10448639430"
	}
}

local KillBottleKey = Enum.KeyCode.Q
local CustomDeathMessages = {
	"LSplash?",
	"1K Knobs = 1 Jiggle LSplash Ballz"
}

-----------------------------------------------------------------------

GuidingLight = string.lower(GuidingLight)

local ReplicatedStorage = game:GetService("ReplicatedStorage")
local Players = game:GetService("Players")

local Cache = game:GetObjects("rbxassetid://78559391457970")[1]
Cache:Destroy()

function setupLight(Child, Color, Icon)
	for _, Thing in pairs(Child:GetDescendants()) do
		if Thing:IsA("ParticleEmitter") then
			Thing.Color = ColorSequence.new(Color)
		elseif Thing:IsA("SpotLight") then
			Thing.Color = Color
		end
	end

	Players.LocalPlayer.PlayerGui.MainUI.Death.HelpfulDialogue.TextColor3 = Color

	Child.Lights.BigLight.Attachment.Moon.Color = ColorSequence.new(Color)
	Child.Lights.BigLight.Attachment.Moon.Texture = Icon
end

local MainGuidingLight = GuidingLights[GuidingLight]
if not MainGuidingLight then
	warn("This Light Does Not Exist!")
	return
end

workspace.CurrentCamera.ChildAdded:Connect(function(Child)
	if string.find(string.lower(Child.Name), "deathbackground") then
		setupLight(Child, MainGuidingLight.Color, MainGuidingLight.Icon)
	end
end)

game:GetService("UserInputService").InputBegan:Connect(function(input, gP)
	if input.KeyCode == KillBottleKey and not gP then
		local StarVile = game:GetObjects("rbxassetid://78559391457970")[1]
		StarVile.Parent = workspace.CurrentRooms[ReplicatedStorage.GameData.LatestRoom.Value]

		StarVile:PivotTo(Players.LocalPlayer.Character.HumanoidRootPart.CFrame)

		StarVile.Union.Color = MainGuidingLight.Color
		StarVile.Union2.Color = MainGuidingLight.Color
		StarVile.ModulePrompt.Triggered:Connect(function()
			if ReplicatedStorage.GameData.LatestRoom.Value >= 1 then
				firesignal(ReplicatedStorage.RemotesFolder.DeathHint.OnClientEvent, CustomDeathMessages, "Blue")
				task.wait(0.5)
				Players.LocalPlayer.Character.Humanoid.Health = 0
			end
		end)
	end
end)

   end,
})

   local Button = BottlesTab:CreateButton({
   Name = "Knob Boost Bottle of Light",
   Callback = function()
   local GuidingLight = "knob boost"
local GuidingLights = {
	["herb"] = {
		Color = Color3.fromRGB(0, 125, 0),
		Icon = "http://www.roblox.com/asset/?id=128170076314731"
	},
	["modifier"] = {
		Color = Color3.fromRGB(229, 118, 114),
		Icon = "rbxassetid://14380950090"
	},
	["revive"] = {
		Color = Color3.fromRGB(224, 92, 98),
		Icon = "rbxassetid://16587986504"
	},
	["gold"] = {
		Color = Color3.fromRGB(249, 237, 159),
		Icon = "rbxassetid://16587947721"
	},
	["knob"] = {
		Color = Color3.fromRGB(232, 143, 138),
		Icon = "rbxassetid://16587915599"
	},
	["knob boost"] = {
		Color = Color3.fromRGB(241, 155, 60),
		Icon = "rbxassetid://10448639430"
	}
}

local KillBottleKey = Enum.KeyCode.Q
local CustomDeathMessages = {
	"Blud",
	"How are you finding us?"
	"Btw - Im Lsplash and floor 3 is not releasing until 2026"
}

-----------------------------------------------------------------------

GuidingLight = string.lower(GuidingLight)

local ReplicatedStorage = game:GetService("ReplicatedStorage")
local Players = game:GetService("Players")

local Cache = game:GetObjects("rbxassetid://78559391457970")[1]
Cache:Destroy()

function setupLight(Child, Color, Icon)
	for _, Thing in pairs(Child:GetDescendants()) do
		if Thing:IsA("ParticleEmitter") then
			Thing.Color = ColorSequence.new(Color)
		elseif Thing:IsA("SpotLight") then
			Thing.Color = Color
		end
	end

	Players.LocalPlayer.PlayerGui.MainUI.Death.HelpfulDialogue.TextColor3 = Color

	Child.Lights.BigLight.Attachment.Moon.Color = ColorSequence.new(Color)
	Child.Lights.BigLight.Attachment.Moon.Texture = Icon
end

local MainGuidingLight = GuidingLights[GuidingLight]
if not MainGuidingLight then
	warn("This Light Does Not Exist!")
	return
end

workspace.CurrentCamera.ChildAdded:Connect(function(Child)
	if string.find(string.lower(Child.Name), "deathbackground") then
		setupLight(Child, MainGuidingLight.Color, MainGuidingLight.Icon)
	end
end)

game:GetService("UserInputService").InputBegan:Connect(function(input, gP)
	if input.KeyCode == KillBottleKey and not gP then
		local StarVile = game:GetObjects("rbxassetid://78559391457970")[1]
		StarVile.Parent = workspace.CurrentRooms[ReplicatedStorage.GameData.LatestRoom.Value]

		StarVile:PivotTo(Players.LocalPlayer.Character.HumanoidRootPart.CFrame)

		StarVile.Union.Color = MainGuidingLight.Color
		StarVile.Union2.Color = MainGuidingLight.Color
		StarVile.ModulePrompt.Triggered:Connect(function()
			if ReplicatedStorage.GameData.LatestRoom.Value >= 1 then
				firesignal(ReplicatedStorage.RemotesFolder.DeathHint.OnClientEvent, CustomDeathMessages, "Blue")
				task.wait(0.5)
				Players.LocalPlayer.Character.Humanoid.Health = 0
			end
		end)
	end
end)

   end,
})

  local Button = BottlesTab:CreateButton({
   Name = "Herb Barrel of light",
   Callback = function()
--[[

LIGHTS:

MODIFIER (Color is Red)
REVIVE (Color is Red)
GOLD (Color is Yellow)
KNOB (Color is Bronze)
KNOB BOOST (Color is Copper)

EXTRA:

Q / EDITED KEY (Spawn StarJug)

]]--

local GuidingLight = "herb"
local GuidingLights = {
  ["herb"] = {
		Color = Color3.fromRGB(0, 125, 0),
		Icon = "http://www.roblox.com/asset/?id=128170076314731"
	},
	["modifier"] = {
		Color = Color3.fromRGB(229, 118, 114),
		Icon = "rbxassetid://14380950090"
	},
	["revive"] = {
		Color = Color3.fromRGB(224, 92, 98),
		Icon = "rbxassetid://16587986504"
	},
	["gold"] = {
		Color = Color3.fromRGB(249, 237, 159),
		Icon = "rbxassetid://16587947721"
	},
	["knob"] = {
		Color = Color3.fromRGB(232, 143, 138),
		Icon = "rbxassetid://16587915599"
	},
	["knob boost"] = {
		Color = Color3.fromRGB(241, 155, 60),
		Icon = "rbxassetid://10448639430"
	}
}

local KillBottleKey = Enum.KeyCode.Q
local CustomDeathMessages = {
	"Yo",
	"Lemme jiggle em ballz - LSplash"
}

-----------------------------------------------------------------------

GuidingLight = string.lower(GuidingLight)

local ReplicatedStorage = game:GetService("ReplicatedStorage")
local Players = game:GetService("Players")

local Cache = game:GetObjects("rbxassetid://125387400084847")[1]
Cache:Destroy()

function setupLight(Child, Color, Icon)
	for _, Thing in pairs(Child:GetDescendants()) do
		if Thing:IsA("ParticleEmitter") then
			Thing.Color = ColorSequence.new(Color)
		elseif Thing:IsA("SpotLight") then
			Thing.Color = Color
		end
	end

	Players.LocalPlayer.PlayerGui.MainUI.Death.HelpfulDialogue.TextColor3 = Color

	Child.Lights.BigLight.Attachment.Moon.Color = ColorSequence.new(Color)
	Child.Lights.BigLight.Attachment.Moon.Texture = Icon
end

local MainGuidingLight = GuidingLights[GuidingLight]
if not MainGuidingLight then
	warn("This Light Does Not Exist!")
	return
end

workspace.CurrentCamera.ChildAdded:Connect(function(Child)
	if string.find(string.lower(Child.Name), "deathbackground") then
		setupLight(Child, MainGuidingLight.Color, MainGuidingLight.Icon)
	end
end)

game:GetService("UserInputService").InputBegan:Connect(function(input, gP)
	if input.KeyCode == KillBottleKey and not gP then
		local StarJug = game:GetObjects("rbxassetid://125387400084847")[1]
		StarJug.Parent = workspace.CurrentRooms[ReplicatedStorage.GameData.LatestRoom.Value]

		StarJug:PivotTo(Players.LocalPlayer.Character.HumanoidRootPart.CFrame)
		
		StarJug.Star.SurfaceGui.ImageLabel.Image = MainGuidingLight.Icon
		StarJug.Liquid.L1.Color = MainGuidingLight.Color
		StarJug.Liquid.L2.Color = MainGuidingLight.Color
		StarJug.Liquid.L3.Color = MainGuidingLight.Color
		StarJug.Liquid.L4.Color = MainGuidingLight.Color
		StarJug.Liquid.L4.Attachment.Triangles.Color = ColorSequence.new(MainGuidingLight.Color)
		StarJug.Liquid.L4.Attachment.ZoomParticle.Color = ColorSequence.new(MainGuidingLight.Color)
		StarJug.Glass.Color = MainGuidingLight.Color
		StarJug.GlassDirt.Color = MainGuidingLight.Color
		
		StarJug.ModulePrompt.Triggered:Connect(function()
			if ReplicatedStorage.GameData.LatestRoom.Value >= 1 then
				StarJug.sound_drink:Play()
				firesignal(ReplicatedStorage.RemotesFolder.DeathHint.OnClientEvent, CustomDeathMessages, "Blue")
				task.wait(0.5)
				Players.LocalPlayer.Character.Humanoid.Health = 0
			end
		end)
	end
end)

   end,
})

  local Button = BottlesTab:CreateButton({
   Name = "Modifier Barrel of light",
   Callback = function()
--[[

LIGHTS:

MODIFIER (Color is Red)
REVIVE (Color is Red)
GOLD (Color is Yellow)
KNOB (Color is Bronze)
KNOB BOOST (Color is Copper)

EXTRA:

Q / EDITED KEY (Spawn StarJug)

]]--

local GuidingLight = "modifier"
local GuidingLights = {
  ["herb"] = {
		Color = Color3.fromRGB(0, 125, 0),
		Icon = "http://www.roblox.com/asset/?id=128170076314731"
	},
	["modifier"] = {
		Color = Color3.fromRGB(229, 118, 114),
		Icon = "rbxassetid://14380950090"
	},
	["revive"] = {
		Color = Color3.fromRGB(224, 92, 98),
		Icon = "rbxassetid://16587986504"
	},
	["gold"] = {
		Color = Color3.fromRGB(249, 237, 159),
		Icon = "rbxassetid://16587947721"
	},
	["knob"] = {
		Color = Color3.fromRGB(232, 143, 138),
		Icon = "rbxassetid://16587915599"
	},
	["knob boost"] = {
		Color = Color3.fromRGB(241, 155, 60),
		Icon = "rbxassetid://10448639430"
	}
}

local KillBottleKey = Enum.KeyCode.Q
local CustomDeathMessages = {
	"Wsp",
	"how many inches are ur ballz?"
}

-----------------------------------------------------------------------

GuidingLight = string.lower(GuidingLight)

local ReplicatedStorage = game:GetService("ReplicatedStorage")
local Players = game:GetService("Players")

local Cache = game:GetObjects("rbxassetid://125387400084847")[1]
Cache:Destroy()

function setupLight(Child, Color, Icon)
	for _, Thing in pairs(Child:GetDescendants()) do
		if Thing:IsA("ParticleEmitter") then
			Thing.Color = ColorSequence.new(Color)
		elseif Thing:IsA("SpotLight") then
			Thing.Color = Color
		end
	end

	Players.LocalPlayer.PlayerGui.MainUI.Death.HelpfulDialogue.TextColor3 = Color

	Child.Lights.BigLight.Attachment.Moon.Color = ColorSequence.new(Color)
	Child.Lights.BigLight.Attachment.Moon.Texture = Icon
end

local MainGuidingLight = GuidingLights[GuidingLight]
if not MainGuidingLight then
	warn("This Light Does Not Exist!")
	return
end

workspace.CurrentCamera.ChildAdded:Connect(function(Child)
	if string.find(string.lower(Child.Name), "deathbackground") then
		setupLight(Child, MainGuidingLight.Color, MainGuidingLight.Icon)
	end
end)

game:GetService("UserInputService").InputBegan:Connect(function(input, gP)
	if input.KeyCode == KillBottleKey and not gP then
		local StarJug = game:GetObjects("rbxassetid://125387400084847")[1]
		StarJug.Parent = workspace.CurrentRooms[ReplicatedStorage.GameData.LatestRoom.Value]

		StarJug:PivotTo(Players.LocalPlayer.Character.HumanoidRootPart.CFrame)
		
		StarJug.Star.SurfaceGui.ImageLabel.Image = MainGuidingLight.Icon
		StarJug.Liquid.L1.Color = MainGuidingLight.Color
		StarJug.Liquid.L2.Color = MainGuidingLight.Color
		StarJug.Liquid.L3.Color = MainGuidingLight.Color
		StarJug.Liquid.L4.Color = MainGuidingLight.Color
		StarJug.Liquid.L4.Attachment.Triangles.Color = ColorSequence.new(MainGuidingLight.Color)
		StarJug.Liquid.L4.Attachment.ZoomParticle.Color = ColorSequence.new(MainGuidingLight.Color)
		StarJug.Glass.Color = MainGuidingLight.Color
		StarJug.GlassDirt.Color = MainGuidingLight.Color
		
		StarJug.ModulePrompt.Triggered:Connect(function()
			if ReplicatedStorage.GameData.LatestRoom.Value >= 1 then
				StarJug.sound_drink:Play()
				firesignal(ReplicatedStorage.RemotesFolder.DeathHint.OnClientEvent, CustomDeathMessages, "Blue")
				task.wait(0.5)
				Players.LocalPlayer.Character.Humanoid.Health = 0
			end
		end)
	end
end)

   end,
})

  local Button = BottlesTab:CreateButton({
   Name = "Revive Barrel of light",
   Callback = function()
--[[

LIGHTS:

MODIFIER (Color is Red)
REVIVE (Color is Red)
GOLD (Color is Yellow)
KNOB (Color is Bronze)
KNOB BOOST (Color is Copper)

EXTRA:

Q / EDITED KEY (Spawn StarJug)

]]--

local GuidingLight = "revive"
local GuidingLights = {
  ["herb"] = {
		Color = Color3.fromRGB(0, 125, 0),
		Icon = "http://www.roblox.com/asset/?id=128170076314731"
	},
	["modifier"] = {
		Color = Color3.fromRGB(229, 118, 114),
		Icon = "rbxassetid://14380950090"
	},
	["revive"] = {
		Color = Color3.fromRGB(224, 92, 98),
		Icon = "rbxassetid://16587986504"
	},
	["gold"] = {
		Color = Color3.fromRGB(249, 237, 159),
		Icon = "rbxassetid://16587947721"
	},
	["knob"] = {
		Color = Color3.fromRGB(232, 143, 138),
		Icon = "rbxassetid://16587915599"
	},
	["knob boost"] = {
		Color = Color3.fromRGB(241, 155, 60),
		Icon = "rbxassetid://10448639430"
	}
}

local KillBottleKey = Enum.KeyCode.Q
local CustomDeathMessages = {
	"Hm...",
	"Hello im revive, I suppose we have not met before.",
	"LEMME JIGGLE UR BALLZ"
}

-----------------------------------------------------------------------

GuidingLight = string.lower(GuidingLight)

local ReplicatedStorage = game:GetService("ReplicatedStorage")
local Players = game:GetService("Players")

local Cache = game:GetObjects("rbxassetid://125387400084847")[1]
Cache:Destroy()

function setupLight(Child, Color, Icon)
	for _, Thing in pairs(Child:GetDescendants()) do
		if Thing:IsA("ParticleEmitter") then
			Thing.Color = ColorSequence.new(Color)
		elseif Thing:IsA("SpotLight") then
			Thing.Color = Color
		end
	end

	Players.LocalPlayer.PlayerGui.MainUI.Death.HelpfulDialogue.TextColor3 = Color

	Child.Lights.BigLight.Attachment.Moon.Color = ColorSequence.new(Color)
	Child.Lights.BigLight.Attachment.Moon.Texture = Icon
end

local MainGuidingLight = GuidingLights[GuidingLight]
if not MainGuidingLight then
	warn("This Light Does Not Exist!")
	return
end

workspace.CurrentCamera.ChildAdded:Connect(function(Child)
	if string.find(string.lower(Child.Name), "deathbackground") then
		setupLight(Child, MainGuidingLight.Color, MainGuidingLight.Icon)
	end
end)

game:GetService("UserInputService").InputBegan:Connect(function(input, gP)
	if input.KeyCode == KillBottleKey and not gP then
		local StarJug = game:GetObjects("rbxassetid://125387400084847")[1]
		StarJug.Parent = workspace.CurrentRooms[ReplicatedStorage.GameData.LatestRoom.Value]

		StarJug:PivotTo(Players.LocalPlayer.Character.HumanoidRootPart.CFrame)
		
		StarJug.Star.SurfaceGui.ImageLabel.Image = MainGuidingLight.Icon
		StarJug.Liquid.L1.Color = MainGuidingLight.Color
		StarJug.Liquid.L2.Color = MainGuidingLight.Color
		StarJug.Liquid.L3.Color = MainGuidingLight.Color
		StarJug.Liquid.L4.Color = MainGuidingLight.Color
		StarJug.Liquid.L4.Attachment.Triangles.Color = ColorSequence.new(MainGuidingLight.Color)
		StarJug.Liquid.L4.Attachment.ZoomParticle.Color = ColorSequence.new(MainGuidingLight.Color)
		StarJug.Glass.Color = MainGuidingLight.Color
		StarJug.GlassDirt.Color = MainGuidingLight.Color
		
		StarJug.ModulePrompt.Triggered:Connect(function()
			if ReplicatedStorage.GameData.LatestRoom.Value >= 1 then
				StarJug.sound_drink:Play()
				firesignal(ReplicatedStorage.RemotesFolder.DeathHint.OnClientEvent, CustomDeathMessages, "Blue")
				task.wait(0.5)
				Players.LocalPlayer.Character.Humanoid.Health = 0
			end
		end)
	end
end)

   end,
})

  local Button = BottlesTab:CreateButton({
   Name = "Gold Barrel of light",
   Callback = function()
--[[

LIGHTS:

MODIFIER (Color is Red)
REVIVE (Color is Red)
GOLD (Color is Yellow)
KNOB (Color is Bronze)
KNOB BOOST (Color is Copper)

EXTRA:

Q / EDITED KEY (Spawn StarJug)

]]--

local GuidingLight = "gold"
local GuidingLights = {
  ["herb"] = {
		Color = Color3.fromRGB(0, 125, 0),
		Icon = "http://www.roblox.com/asset/?id=128170076314731"
	},
	["modifier"] = {
		Color = Color3.fromRGB(229, 118, 114),
		Icon = "rbxassetid://14380950090"
	},
	["revive"] = {
		Color = Color3.fromRGB(224, 92, 98),
		Icon = "rbxassetid://16587986504"
	},
	["gold"] = {
		Color = Color3.fromRGB(249, 237, 159),
		Icon = "rbxassetid://16587947721"
	},
	["knob"] = {
		Color = Color3.fromRGB(232, 143, 138),
		Icon = "rbxassetid://16587915599"
	},
	["knob boost"] = {
		Color = Color3.fromRGB(241, 155, 60),
		Icon = "rbxassetid://10448639430"
	}
}

local KillBottleKey = Enum.KeyCode.Q
local CustomDeathMessages = {
	"Wassup Bro",
	"Im Gold aka the master of jiggleing Ballz",
	"Can i jiggle yous?"
}

-----------------------------------------------------------------------

GuidingLight = string.lower(GuidingLight)

local ReplicatedStorage = game:GetService("ReplicatedStorage")
local Players = game:GetService("Players")

local Cache = game:GetObjects("rbxassetid://125387400084847")[1]
Cache:Destroy()

function setupLight(Child, Color, Icon)
	for _, Thing in pairs(Child:GetDescendants()) do
		if Thing:IsA("ParticleEmitter") then
			Thing.Color = ColorSequence.new(Color)
		elseif Thing:IsA("SpotLight") then
			Thing.Color = Color
		end
	end

	Players.LocalPlayer.PlayerGui.MainUI.Death.HelpfulDialogue.TextColor3 = Color

	Child.Lights.BigLight.Attachment.Moon.Color = ColorSequence.new(Color)
	Child.Lights.BigLight.Attachment.Moon.Texture = Icon
end

local MainGuidingLight = GuidingLights[GuidingLight]
if not MainGuidingLight then
	warn("This Light Does Not Exist!")
	return
end

workspace.CurrentCamera.ChildAdded:Connect(function(Child)
	if string.find(string.lower(Child.Name), "deathbackground") then
		setupLight(Child, MainGuidingLight.Color, MainGuidingLight.Icon)
	end
end)

game:GetService("UserInputService").InputBegan:Connect(function(input, gP)
	if input.KeyCode == KillBottleKey and not gP then
		local StarJug = game:GetObjects("rbxassetid://125387400084847")[1]
		StarJug.Parent = workspace.CurrentRooms[ReplicatedStorage.GameData.LatestRoom.Value]

		StarJug:PivotTo(Players.LocalPlayer.Character.HumanoidRootPart.CFrame)
		
		StarJug.Star.SurfaceGui.ImageLabel.Image = MainGuidingLight.Icon
		StarJug.Liquid.L1.Color = MainGuidingLight.Color
		StarJug.Liquid.L2.Color = MainGuidingLight.Color
		StarJug.Liquid.L3.Color = MainGuidingLight.Color
		StarJug.Liquid.L4.Color = MainGuidingLight.Color
		StarJug.Liquid.L4.Attachment.Triangles.Color = ColorSequence.new(MainGuidingLight.Color)
		StarJug.Liquid.L4.Attachment.ZoomParticle.Color = ColorSequence.new(MainGuidingLight.Color)
		StarJug.Glass.Color = MainGuidingLight.Color
		StarJug.GlassDirt.Color = MainGuidingLight.Color
		
		StarJug.ModulePrompt.Triggered:Connect(function()
			if ReplicatedStorage.GameData.LatestRoom.Value >= 1 then
				StarJug.sound_drink:Play()
				firesignal(ReplicatedStorage.RemotesFolder.DeathHint.OnClientEvent, CustomDeathMessages, "Blue")
				task.wait(0.5)
				Players.LocalPlayer.Character.Humanoid.Health = 0
			end
		end)
	end
end)

   end,
})

  local Button = BottlesTab:CreateButton({
   Name = "Knob Barrel of light",
   Callback = function()
--[[

LIGHTS:

MODIFIER (Color is Red)
REVIVE (Color is Red)
GOLD (Color is Yellow)
KNOB (Color is Bronze)
KNOB BOOST (Color is Copper)

EXTRA:

Q / EDITED KEY (Spawn StarJug)

]]--

local GuidingLight = "knob"
local GuidingLights = {
  ["herb"] = {
		Color = Color3.fromRGB(0, 125, 0),
		Icon = "http://www.roblox.com/asset/?id=128170076314731"
	},
	["modifier"] = {
		Color = Color3.fromRGB(229, 118, 114),
		Icon = "rbxassetid://14380950090"
	},
	["revive"] = {
		Color = Color3.fromRGB(224, 92, 98),
		Icon = "rbxassetid://16587986504"
	},
	["gold"] = {
		Color = Color3.fromRGB(249, 237, 159),
		Icon = "rbxassetid://16587947721"
	},
	["knob"] = {
		Color = Color3.fromRGB(232, 143, 138),
		Icon = "rbxassetid://16587915599"
	},
	["knob boost"] = {
		Color = Color3.fromRGB(241, 155, 60),
		Icon = "rbxassetid://10448639430"
	}
}

local KillBottleKey = Enum.KeyCode.Q
local CustomDeathMessages = {
	"Blud",
	"I can Suck UR Dick through your ass",
}

-----------------------------------------------------------------------

GuidingLight = string.lower(GuidingLight)

local ReplicatedStorage = game:GetService("ReplicatedStorage")
local Players = game:GetService("Players")

local Cache = game:GetObjects("rbxassetid://125387400084847")[1]
Cache:Destroy()

function setupLight(Child, Color, Icon)
	for _, Thing in pairs(Child:GetDescendants()) do
		if Thing:IsA("ParticleEmitter") then
			Thing.Color = ColorSequence.new(Color)
		elseif Thing:IsA("SpotLight") then
			Thing.Color = Color
		end
	end

	Players.LocalPlayer.PlayerGui.MainUI.Death.HelpfulDialogue.TextColor3 = Color

	Child.Lights.BigLight.Attachment.Moon.Color = ColorSequence.new(Color)
	Child.Lights.BigLight.Attachment.Moon.Texture = Icon
end

local MainGuidingLight = GuidingLights[GuidingLight]
if not MainGuidingLight then
	warn("This Light Does Not Exist!")
	return
end

workspace.CurrentCamera.ChildAdded:Connect(function(Child)
	if string.find(string.lower(Child.Name), "deathbackground") then
		setupLight(Child, MainGuidingLight.Color, MainGuidingLight.Icon)
	end
end)

game:GetService("UserInputService").InputBegan:Connect(function(input, gP)
	if input.KeyCode == KillBottleKey and not gP then
		local StarJug = game:GetObjects("rbxassetid://125387400084847")[1]
		StarJug.Parent = workspace.CurrentRooms[ReplicatedStorage.GameData.LatestRoom.Value]

		StarJug:PivotTo(Players.LocalPlayer.Character.HumanoidRootPart.CFrame)
		
		StarJug.Star.SurfaceGui.ImageLabel.Image = MainGuidingLight.Icon
		StarJug.Liquid.L1.Color = MainGuidingLight.Color
		StarJug.Liquid.L2.Color = MainGuidingLight.Color
		StarJug.Liquid.L3.Color = MainGuidingLight.Color
		StarJug.Liquid.L4.Color = MainGuidingLight.Color
		StarJug.Liquid.L4.Attachment.Triangles.Color = ColorSequence.new(MainGuidingLight.Color)
		StarJug.Liquid.L4.Attachment.ZoomParticle.Color = ColorSequence.new(MainGuidingLight.Color)
		StarJug.Glass.Color = MainGuidingLight.Color
		StarJug.GlassDirt.Color = MainGuidingLight.Color
		
		StarJug.ModulePrompt.Triggered:Connect(function()
			if ReplicatedStorage.GameData.LatestRoom.Value >= 1 then
				StarJug.sound_drink:Play()
				firesignal(ReplicatedStorage.RemotesFolder.DeathHint.OnClientEvent, CustomDeathMessages, "Blue")
				task.wait(0.5)
				Players.LocalPlayer.Character.Humanoid.Health = 0
			end
		end)
	end
end)

   end,
})

  local Button = BottlesTab:CreateButton({
   Name = "Knob Boost Barrel of light",
   Callback = function()
--[[

LIGHTS:

MODIFIER (Color is Red)
REVIVE (Color is Red)
GOLD (Color is Yellow)
KNOB (Color is Bronze)
KNOB BOOST (Color is Copper)

EXTRA:

Q / EDITED KEY (Spawn StarJug)

]]--

local GuidingLight = "knob boost"
local GuidingLights = {
  ["herb"] = {
		Color = Color3.fromRGB(0, 125, 0),
		Icon = "http://www.roblox.com/asset/?id=128170076314731"
	},
	["modifier"] = {
		Color = Color3.fromRGB(229, 118, 114),
		Icon = "rbxassetid://14380950090"
	},
	["revive"] = {
		Color = Color3.fromRGB(224, 92, 98),
		Icon = "rbxassetid://16587986504"
	},
	["gold"] = {
		Color = Color3.fromRGB(249, 237, 159),
		Icon = "rbxassetid://16587947721"
	},
	["knob"] = {
		Color = Color3.fromRGB(232, 143, 138),
		Icon = "rbxassetid://16587915599"
	},
	["knob boost"] = {
		Color = Color3.fromRGB(241, 155, 60),
		Icon = "rbxassetid://10448639430"
	}
}

local KillBottleKey = Enum.KeyCode.Q
local CustomDeathMessages = {
	"Bro",
	"How are you finding us?",
	"Btw im LSplash and floor 3 is not releasing until 2027"
}

-----------------------------------------------------------------------

GuidingLight = string.lower(GuidingLight)

local ReplicatedStorage = game:GetService("ReplicatedStorage")
local Players = game:GetService("Players")

local Cache = game:GetObjects("rbxassetid://125387400084847")[1]
Cache:Destroy()

function setupLight(Child, Color, Icon)
	for _, Thing in pairs(Child:GetDescendants()) do
		if Thing:IsA("ParticleEmitter") then
			Thing.Color = ColorSequence.new(Color)
		elseif Thing:IsA("SpotLight") then
			Thing.Color = Color
		end
	end

	Players.LocalPlayer.PlayerGui.MainUI.Death.HelpfulDialogue.TextColor3 = Color

	Child.Lights.BigLight.Attachment.Moon.Color = ColorSequence.new(Color)
	Child.Lights.BigLight.Attachment.Moon.Texture = Icon
end

local MainGuidingLight = GuidingLights[GuidingLight]
if not MainGuidingLight then
	warn("This Light Does Not Exist!")
	return
end

workspace.CurrentCamera.ChildAdded:Connect(function(Child)
	if string.find(string.lower(Child.Name), "deathbackground") then
		setupLight(Child, MainGuidingLight.Color, MainGuidingLight.Icon)
	end
end)

game:GetService("UserInputService").InputBegan:Connect(function(input, gP)
	if input.KeyCode == KillBottleKey and not gP then
		local StarJug = game:GetObjects("rbxassetid://125387400084847")[1]
		StarJug.Parent = workspace.CurrentRooms[ReplicatedStorage.GameData.LatestRoom.Value]

		StarJug:PivotTo(Players.LocalPlayer.Character.HumanoidRootPart.CFrame)
		
		StarJug.Star.SurfaceGui.ImageLabel.Image = MainGuidingLight.Icon
		StarJug.Liquid.L1.Color = MainGuidingLight.Color
		StarJug.Liquid.L2.Color = MainGuidingLight.Color
		StarJug.Liquid.L3.Color = MainGuidingLight.Color
		StarJug.Liquid.L4.Color = MainGuidingLight.Color
		StarJug.Liquid.L4.Attachment.Triangles.Color = ColorSequence.new(MainGuidingLight.Color)
		StarJug.Liquid.L4.Attachment.ZoomParticle.Color = ColorSequence.new(MainGuidingLight.Color)
		StarJug.Glass.Color = MainGuidingLight.Color
		StarJug.GlassDirt.Color = MainGuidingLight.Color
		
		StarJug.ModulePrompt.Triggered:Connect(function()
			if ReplicatedStorage.GameData.LatestRoom.Value >= 1 then
				StarJug.sound_drink:Play()
				firesignal(ReplicatedStorage.RemotesFolder.DeathHint.OnClientEvent, CustomDeathMessages, "Blue")
				task.wait(0.5)
				Players.LocalPlayer.Character.Humanoid.Health = 0
			end
		end)
	end
end)

   end,
})

local PlushysTab = Window:CreateTab("Plushys", "package-open")
local PlushysSection = PlushysTab:CreateSection("Plushys")

   local Button = PlushysTab:CreateButton({
   Name = "Rush Plushy",
   Callback = function()
    --[[

RUSH
AMBUSH
JACK
DUPE

]]--

local RushEnabled = true
local AmbushEnabled = false
local JackEnabled = false
local DupeEnabled = false

---------------------------------------------------------

local Players = game:GetService("Players")
local UIS = game:GetService("UserInputService")
local Plr = Players.LocalPlayer
local Char = Plr.Character or Plr.CharacterAdded:Wait()

local Rush = game:GetObjects("rbxassetid://106490395325401")[1]
if RushEnabled then
	Rush.Parent = game.Players.LocalPlayer.Backpack
end

local Ambush = game:GetObjects("rbxassetid://91769363360905")[1]
if AmbushEnabled then
	Ambush.Parent = game.Players.LocalPlayer.Backpack
end

local Jack = game:GetObjects("rbxassetid://135816582968851")[1]
if JackEnabled then
	Jack.Parent = game.Players.LocalPlayer.Backpack
end

local Dupe = game:GetObjects("rbxassetid://116858052599982")[1]
if DupeEnabled then
	Dupe.Parent = game.Players.LocalPlayer.Backpack
end
   end,
})

   local Button = PlushysTab:CreateButton({
   Name = "Ambush Plushy",
   Callback = function()
    --[[

RUSH
AMBUSH
JACK
DUPE

]]--

local RushEnabled = false
local AmbushEnabled = true
local JackEnabled = false
local DupeEnabled = false

---------------------------------------------------------

local Players = game:GetService("Players")
local UIS = game:GetService("UserInputService")
local Plr = Players.LocalPlayer
local Char = Plr.Character or Plr.CharacterAdded:Wait()

local Rush = game:GetObjects("rbxassetid://106490395325401")[1]
if RushEnabled then
	Rush.Parent = game.Players.LocalPlayer.Backpack
end

local Ambush = game:GetObjects("rbxassetid://91769363360905")[1]
if AmbushEnabled then
	Ambush.Parent = game.Players.LocalPlayer.Backpack
end

local Jack = game:GetObjects("rbxassetid://135816582968851")[1]
if JackEnabled then
	Jack.Parent = game.Players.LocalPlayer.Backpack
end

local Dupe = game:GetObjects("rbxassetid://116858052599982")[1]
if DupeEnabled then
	Dupe.Parent = game.Players.LocalPlayer.Backpack
end
   end,
})

   local Button = PlushysTab:CreateButton({
   Name = "Dupe Plushy",
   Callback = function()
    --[[

RUSH
AMBUSH
JACK
DUPE

]]--

local RushEnabled = false
local AmbushEnabled = false
local JackEnabled = false
local DupeEnabled = true

---------------------------------------------------------

local Players = game:GetService("Players")
local UIS = game:GetService("UserInputService")
local Plr = Players.LocalPlayer
local Char = Plr.Character or Plr.CharacterAdded:Wait()

local Rush = game:GetObjects("rbxassetid://106490395325401")[1]
if RushEnabled then
	Rush.Parent = game.Players.LocalPlayer.Backpack
end

local Ambush = game:GetObjects("rbxassetid://91769363360905")[1]
if AmbushEnabled then
	Ambush.Parent = game.Players.LocalPlayer.Backpack
end

local Jack = game:GetObjects("rbxassetid://135816582968851")[1]
if JackEnabled then
	Jack.Parent = game.Players.LocalPlayer.Backpack
end

local Dupe = game:GetObjects("rbxassetid://116858052599982")[1]
if DupeEnabled then
	Dupe.Parent = game.Players.LocalPlayer.Backpack
end
   end,
})

  local Button = PlushysTab:CreateButton({
   Name = "Seek Plushy",
   Callback = function()
    local plr = game.Players.LocalPlayer
local hum = plr.Character:WaitForChild("Humanoid")

local plush = game:GetObjects("rbxassetid://13613269677")[1]
plush.Parent = plr.Backpack
local anim = hum:LoadAnimation(plush.A.Hold)

plush.Equipped:Connect(function()
  anim:Play()
end)
plush.Unequipped:Connect(function()
  anim:Stop()
end)

plush.Activated:Connect(function()
  plush.Toy:Play()
end)

   end,
})
 
   local Button = PlushysTab:CreateButton({
   Name = "Depth Plushy",
   Callback = function()
    local plr = game.Players.LocalPlayer
  local Players = game:GetService("Players")
local Equipped = false
local Plr = Players.LocalPlayer
local Char = Plr.Character or Plr.CharacterAdded:Wait()
local Hum = Char:WaitForChild("Humanoid")
local Root = Char:WaitForChild("HumanoidRootPart")
local RightArm = Char:WaitForChild("RightUpperArm")
local LeftArm = Char:WaitForChild("LeftUpperArm")
local RightC1 = RightArm.RightShoulder.C1
local LeftC1 = LeftArm.LeftShoulder.C1
local Functions = loadstring(game:HttpGet("https://raw.githubusercontent.com/RegularVynixu/Utilities/main/Functions.lua"))()
local CustomShop = loadstring(game:HttpGet("https://raw.githubusercontent.com/MateiDaBest/Utilities/main/Doors/Custom%20Shop%20Items/Main.lua"))()
local Depth = game:GetObjects("rbxassetid://12564733947")[1]
local Atmosphere = Instance.new("Atmosphere")

Atmosphere.Density = 0.75
Atmosphere.Parent = game.ReplicatedStorage

CustomShop.CreateItem({
	Title = "Depth Plushy",
	Desc = "Soft And Squishy, Get One Today! - made in China",
	Image = "https://tr.rbxcdn.com/53282d5b0b4878d45e3ad63683961eae/420/420/Hat/Webp",
	Price = 69,
	Stack = 1,
})

Depth.Parent = game.Players.LocalPlayer.Backpack

local function setupHands(tool)
	tool.Equipped:Connect(function()
		Equipped = true
		Char:SetAttribute("Hiding", true)
		for _, v in next, Hum:GetPlayingAnimationTracks() do
			v:Stop()
		end

		RightArm.Name = "R_Arm"
		LeftArm.Name = "L_Arm"

		RightArm.RightShoulder.C1 = RightC1
			* CFrame.Angles(math.rad(-90), math.rad(-10), 0)
		LeftArm.LeftShoulder.C1 = LeftC1
			* CFrame.new(-0.2, 0.1, -0.5)
			* CFrame.Angles(math.rad(-110), math.rad(15), math.rad(0))

		Atmosphere.Parent = game.Lighting

		for i, object in pairs(workspace:WaitForChild("CurrentRooms"):GetDescendants()) do
			if object.Name == "Neon" then
				object.Color = Color3.new(0.333333, 0.666667, 1)
			end
		end
	end)

	tool.Unequipped:Connect(function()
		Equipped = false
		Char:SetAttribute("Hiding", nil)
		RightArm.Name = "RightUpperArm"
		LeftArm.Name = "LeftUpperArm"

		RightArm.RightShoulder.C1 = RightC1
		LeftArm.LeftShoulder.C1 = LeftC1

		Atmosphere.Parent = game.ReplicatedStorage

		for i, object in pairs(workspace:WaitForChild("CurrentRooms"):GetDescendants()) do
			if object.Name == "Neon" then
				object.Color = Color3.new(0.764706, 0.631373, 0.552941)
			end
		end
	end)
end

setupHands(Depth)
   end,
})
 
  local Button = PlushysTab:CreateButton({
   Name = "A-60 Plushy",
   Callback = function()
local Players = game:GetService("Players")
local UIS = game:GetService("UserInputService")
local Plr = Players.LocalPlayer
local Char = Plr.Character or Plr.CharacterAdded:Wait()

local shadow = game:GetObjects("rbxassetid://85674900664881")[1]
shadow.Parent = game.Players.LocalPlayer.Backpack

UIS.InputBegan:Connect(function(input, gameProcessed)
	if not gameProcessed and input.KeyCode == Enum.KeyCode.Space then
		local plushie = Char:FindFirstChild("A60")

		if plushie then
			plushie.Handle.Sound:Stop()
		end
	end
end)

UIS.InputBegan:Connect(function(input, gameProcessed)
	if not gameProcessed and input.KeyCode == Enum.KeyCode.K then
		local plushie = Char:FindFirstChild("A60")

		if plushie then
			plushie.Handle.Sound:Play()
		end
	end
end)
   end,
})
 
 local Button = PlushysTab:CreateButton({
   Name = "A-90 Plushy",
   Callback = function()
local Players = game:GetService("Players")
local Equipped = false
local Plr = Players.LocalPlayer
local Char = Plr.Character or Plr.CharacterAdded:Wait()
local Hum = Char:WaitForChild("Humanoid")
local Root = Char:WaitForChild("HumanoidRootPart")
local RightArm = Char:WaitForChild("RightUpperArm")
local LeftArm = Char:WaitForChild("LeftUpperArm")
local RightC1 = RightArm.RightShoulder.C1
local LeftC1 = LeftArm.LeftShoulder.C1
local A90 = game:GetObjects("rbxassetid://12544988486")[1]

A90.Parent = game.Players.LocalPlayer.Backpack

local function setupHands(tool)
	tool.Equipped:Connect(function()
		Equipped = true
		Char:SetAttribute("Hiding", true)
		for _, v in next, Hum:GetPlayingAnimationTracks() do
			v:Stop()
		end

		RightArm.Name = "R_Arm"
		LeftArm.Name = "L_Arm"

		RightArm.RightShoulder.C1 = RightC1
			* CFrame.Angles(math.rad(-90), math.rad(-10), 0)
		LeftArm.LeftShoulder.C1 = LeftC1
			* CFrame.new(-0.2, 0, -0.5)
			* CFrame.Angles(math.rad(-110), math.rad(15), math.rad(0))
	end)

	tool.Unequipped:Connect(function()
		Equipped = false
		Char:SetAttribute("Hiding", nil)
		RightArm.Name = "RightUpperArm"
		LeftArm.Name = "LeftUpperArm"

		RightArm.RightShoulder.C1 = RightC1
		LeftArm.LeftShoulder.C1 = LeftC1
	end)
end

setupHands(A90)
   end,
})

  local Button = PlushysTab:CreateButton({
   Name = "A-120 Plushy",
   Callback = function()
     local Players = game:GetService("Players")
local Equipped = false
local Plr = Players.LocalPlayer
local Char = Plr.Character or Plr.CharacterAdded:Wait()
local Hum = Char:WaitForChild("Humanoid")
local Root = Char:WaitForChild("HumanoidRootPart")
local RightArm = Char:WaitForChild("RightUpperArm")
local LeftArm = Char:WaitForChild("LeftUpperArm")
local RightC1 = RightArm.RightShoulder.C1
local LeftC1 = LeftArm.LeftShoulder.C1
local Functions = loadstring(game:HttpGet("https://raw.githubusercontent.com/RegularVynixu/Utilities/main/Functions.lua"))()
local CustomShop = loadstring(game:HttpGet("https://raw.githubusercontent.com/MateiDaBest/Utilities/main/Doors/Custom%20Shop%20Items/Main.lua"))()
local A120 = game:GetObjects("rbxassetid://12564739530")[1]

CustomShop.CreateItem({
	Title = "A-120 Plushie",
	Desc = "Soft And Squishy, Get One Today! - made in China",
	Image = "https://i.pinimg.com/236x/76/ed/02/76ed02350afbd78b8275743958871368.jpg",
	Price = 69,
	Stack = 1,
})

A120.Parent = game.Players.LocalPlayer.Backpack

local function setupHands(tool)
	tool.Equipped:Connect(function()
		Equipped = true
		Char:SetAttribute("Hiding", true)
		for _, v in next, Hum:GetPlayingAnimationTracks() do
			v:Stop()
		end

		RightArm.Name = "R_Arm"
		LeftArm.Name = "L_Arm"

		RightArm.RightShoulder.C1 = RightC1
			* CFrame.Angles(math.rad(-90), math.rad(-10), 0)
		LeftArm.LeftShoulder.C1 = LeftC1
			* CFrame.new(-0.2, 0, -0.5)
			* CFrame.Angles(math.rad(-110), math.rad(15), math.rad(0))
	end)

	tool.Unequipped:Connect(function()
		Equipped = false
		Char:SetAttribute("Hiding", nil)
		RightArm.Name = "RightUpperArm"
		LeftArm.Name = "LeftUpperArm"

		RightArm.RightShoulder.C1 = RightC1
		LeftArm.LeftShoulder.C1 = LeftC1
	end)
end

setupHands(A120)
   end,
})

   local Button = PlushysTab:CreateButton({
   Name = "Green Blitz Plushy",
   Callback = function()
    --[[

HASTE + DOUBLE BLITZ PLUSHIES

[K] - PLAY SOUNDS
[SPACE] - STOP SOUNDS

]]--

local Sounds = true

local HasteEnabled = false
local BrotherEnabled = true
local SisterEnabled = false

local SoundKey = Enum.KeyCode.K
local StopSoundKey = Enum.KeyCode.Space

---------------------------------------------------------

local Players = game:GetService("Players")
local UIS = game:GetService("UserInputService")
local Plr = Players.LocalPlayer
local Char = Plr.Character or Plr.CharacterAdded:Wait()

local Haste = game:GetObjects("rbxassetid://109374845896295")[1]
if HasteEnabled then
	Haste.Parent = game.Players.LocalPlayer.Backpack
end

local Brother = game:GetObjects("rbxassetid://81472152992030")[1]
if BrotherEnabled then
	Brother.Parent = game.Players.LocalPlayer.Backpack
end

local Sister = game:GetObjects("rbxassetid://85239321727099")[1]
if SisterEnabled then
	Sister.Parent = game.Players.LocalPlayer.Backpack
end

if Sounds then
	Haste.Handle.Sound.SoundId = getsynasset("Sounds/Haste.MP3")
	Brother.Handle.Sound.SoundId = getsynasset("Sounds/Blitz.MP3")
	Sister.Handle.Sound.SoundId = getsynasset("Sounds/Blitz.MP3")
end

UIS.InputBegan:Connect(function(input, gameProcessed)
	if not gameProcessed and input.KeyCode == StopSoundKey then
		local HastePlushie = Char:FindFirstChild(Haste.Name)
		local BrotherPlushie = Char:FindFirstChild(Brother.Name)
		local SisterPlushie = Char:FindFirstChild(Sister.Name)
		
		if HastePlushie then
			HastePlushie.Handle.Sound:Stop()
		end
		
		if BrotherPlushie then
			BrotherPlushie.Handle.Sound:Stop()
		end

		if SisterPlushie then
			SisterPlushie.Handle.Sound:Stop()
		end
	end
end)

UIS.InputBegan:Connect(function(input, gameProcessed)
	if not gameProcessed and input.KeyCode == SoundKey then
		local HastePlushie = Char:FindFirstChild(Haste.Name)
		local BrotherPlushie = Char:FindFirstChild(Brother.Name)
		local SisterPlushie = Char:FindFirstChild(Sister.Name)

		if HastePlushie then
			HastePlushie.Handle.Sound:Play()
		end

		if BrotherPlushie then
			BrotherPlushie.Handle.Sound:Play()
		end

		if SisterPlushie then
			SisterPlushie.Handle.Sound:Play()
		end
	end
end)
   end,
})

   local Button = PlushysTab:CreateButton({
   Name = "Pink Blitz Plushy",
   Callback = function()
    --[[

HASTE + DOUBLE BLITZ PLUSHIES

[K] - PLAY SOUNDS
[SPACE] - STOP SOUNDS

]]--

local Sounds = true

local HasteEnabled = false
local BrotherEnabled = false
local SisterEnabled = true

local SoundKey = Enum.KeyCode.K
local StopSoundKey = Enum.KeyCode.Space

---------------------------------------------------------

local Players = game:GetService("Players")
local UIS = game:GetService("UserInputService")
local Plr = Players.LocalPlayer
local Char = Plr.Character or Plr.CharacterAdded:Wait()

local Haste = game:GetObjects("rbxassetid://109374845896295")[1]
if HasteEnabled then
	Haste.Parent = game.Players.LocalPlayer.Backpack
end

local Brother = game:GetObjects("rbxassetid://81472152992030")[1]
if BrotherEnabled then
	Brother.Parent = game.Players.LocalPlayer.Backpack
end

local Sister = game:GetObjects("rbxassetid://85239321727099")[1]
if SisterEnabled then
	Sister.Parent = game.Players.LocalPlayer.Backpack
end

if Sounds then
	Haste.Handle.Sound.SoundId = getsynasset("Sounds/Haste.MP3")
	Brother.Handle.Sound.SoundId = getsynasset("Sounds/Blitz.MP3")
	Sister.Handle.Sound.SoundId = getsynasset("Sounds/Blitz.MP3")
end

UIS.InputBegan:Connect(function(input, gameProcessed)
	if not gameProcessed and input.KeyCode == StopSoundKey then
		local HastePlushie = Char:FindFirstChild(Haste.Name)
		local BrotherPlushie = Char:FindFirstChild(Brother.Name)
		local SisterPlushie = Char:FindFirstChild(Sister.Name)
		
		if HastePlushie then
			HastePlushie.Handle.Sound:Stop()
		end
		
		if BrotherPlushie then
			BrotherPlushie.Handle.Sound:Stop()
		end

		if SisterPlushie then
			SisterPlushie.Handle.Sound:Stop()
		end
	end
end)

UIS.InputBegan:Connect(function(input, gameProcessed)
	if not gameProcessed and input.KeyCode == SoundKey then
		local HastePlushie = Char:FindFirstChild(Haste.Name)
		local BrotherPlushie = Char:FindFirstChild(Brother.Name)
		local SisterPlushie = Char:FindFirstChild(Sister.Name)

		if HastePlushie then
			HastePlushie.Handle.Sound:Play()
		end

		if BrotherPlushie then
			BrotherPlushie.Handle.Sound:Play()
		end

		if SisterPlushie then
			SisterPlushie.Handle.Sound:Play()
		end
	end
end)
   end,
})

   local Button = PlushysTab:CreateButton({
   Name = "Haste Plushy",
   Callback = function()
    --[[

HASTE + DOUBLE BLITZ PLUSHIES

[K] - PLAY SOUNDS
[SPACE] - STOP SOUNDS

]]--

local Sounds = true

local HasteEnabled = true
local BrotherEnabled = false
local SisterEnabled = false

local SoundKey = Enum.KeyCode.K
local StopSoundKey = Enum.KeyCode.Space

---------------------------------------------------------

local Players = game:GetService("Players")
local UIS = game:GetService("UserInputService")
local Plr = Players.LocalPlayer
local Char = Plr.Character or Plr.CharacterAdded:Wait()

local Haste = game:GetObjects("rbxassetid://109374845896295")[1]
if HasteEnabled then
	Haste.Parent = game.Players.LocalPlayer.Backpack
end

local Brother = game:GetObjects("rbxassetid://81472152992030")[1]
if BrotherEnabled then
	Brother.Parent = game.Players.LocalPlayer.Backpack
end

local Sister = game:GetObjects("rbxassetid://85239321727099")[1]
if SisterEnabled then
	Sister.Parent = game.Players.LocalPlayer.Backpack
end

if Sounds then
	Haste.Handle.Sound.SoundId = getsynasset("Sounds/Haste.MP3")
	Brother.Handle.Sound.SoundId = getsynasset("Sounds/Blitz.MP3")
	Sister.Handle.Sound.SoundId = getsynasset("Sounds/Blitz.MP3")
end

UIS.InputBegan:Connect(function(input, gameProcessed)
	if not gameProcessed and input.KeyCode == StopSoundKey then
		local HastePlushie = Char:FindFirstChild(Haste.Name)
		local BrotherPlushie = Char:FindFirstChild(Brother.Name)
		local SisterPlushie = Char:FindFirstChild(Sister.Name)
		
		if HastePlushie then
			HastePlushie.Handle.Sound:Stop()
		end
		
		if BrotherPlushie then
			BrotherPlushie.Handle.Sound:Stop()
		end

		if SisterPlushie then
			SisterPlushie.Handle.Sound:Stop()
		end
	end
end)

UIS.InputBegan:Connect(function(input, gameProcessed)
	if not gameProcessed and input.KeyCode == SoundKey then
		local HastePlushie = Char:FindFirstChild(Haste.Name)
		local BrotherPlushie = Char:FindFirstChild(Brother.Name)
		local SisterPlushie = Char:FindFirstChild(Sister.Name)

		if HastePlushie then
			HastePlushie.Handle.Sound:Play()
		end

		if BrotherPlushie then
			BrotherPlushie.Handle.Sound:Play()
		end

		if SisterPlushie then
			SisterPlushie.Handle.Sound:Play()
		end
	end
end)
   end,
})

   local Button = PlushysTab:CreateButton({
   Name = "Jack Plushy",
   Callback = function()
    --[[

RUSH
AMBUSH
JACK
DUPE

]]--

local RushEnabled = false
local AmbushEnabled = false
local JackEnabled = true
local DupeEnabled = false

---------------------------------------------------------

local Players = game:GetService("Players")
local UIS = game:GetService("UserInputService")
local Plr = Players.LocalPlayer
local Char = Plr.Character or Plr.CharacterAdded:Wait()

local Rush = game:GetObjects("rbxassetid://106490395325401")[1]
if RushEnabled then
	Rush.Parent = game.Players.LocalPlayer.Backpack
end

local Ambush = game:GetObjects("rbxassetid://91769363360905")[1]
if AmbushEnabled then
	Ambush.Parent = game.Players.LocalPlayer.Backpack
end

local Jack = game:GetObjects("rbxassetid://135816582968851")[1]
if JackEnabled then
	Jack.Parent = game.Players.LocalPlayer.Backpack
end

local Dupe = game:GetObjects("rbxassetid://116858052599982")[1]
if DupeEnabled then
	Dupe.Parent = game.Players.LocalPlayer.Backpack
end
   end,
})

   local Button = PlushysTab:CreateButton({
   Name = "El Goblino Plushy",
   Callback = function()
local Players = game:GetService("Players")
local Equipped = false
local Plr = Players.LocalPlayer
local Char = Plr.Character or Plr.CharacterAdded:Wait()
local Hum = Char:WaitForChild("Humanoid")
local Root = Char:WaitForChild("HumanoidRootPart")
local RightArm = Char:WaitForChild("RightUpperArm")
local LeftArm = Char:WaitForChild("LeftUpperArm")
local RightC1 = RightArm.RightShoulder.C1
local LeftC1 = LeftArm.LeftShoulder.C1
local CustomShop = loadstring(game:HttpGet("https://raw.githubusercontent.com/MateiDaBest/Utilities/main/Doors/Custom%20Shop%20Items/Main.lua"))()
local Goblino = game:GetObjects("rbxassetid://12856605563")[1]

Goblino.Parent = game.Players.LocalPlayer.Backpack

CustomShop.CreateItem({
	Title = "El Goblino",
	Desc = "Door 52",
	Image = "https://cdn.discordapp.com/attachments/970078853127110677/1087774910706888824/12372522258.png",
	Price = 52,
	Stack = 1,
})

local function setupHands(tool)
	tool.Equipped:Connect(function()
		Equipped = true
		Char:SetAttribute("Hiding", true)
		for _, v in next, Hum:GetPlayingAnimationTracks() do
			v:Stop()
		end

		RightArm.Name = "R_Arm"
		LeftArm.Name = "L_Arm"

		RightArm.RightShoulder.C1 = RightC1
			* CFrame.Angles(math.rad(-90), math.rad(-10), 0)
		LeftArm.LeftShoulder.C1 = LeftC1
			* CFrame.new(-0.2, -0.4, -0.5)
			* CFrame.Angles(math.rad(-110), math.rad(30), math.rad(0))	
	end)

	tool.Unequipped:Connect(function()
		Equipped = false
		Char:SetAttribute("Hiding", nil)
		RightArm.Name = "RightUpperArm"
		LeftArm.Name = "LeftUpperArm"

		RightArm.RightShoulder.C1 = RightC1
		LeftArm.LeftShoulder.C1 = LeftC1
	end)
end

setupHands(Goblino)
   end,
})
 
   local Button = PlushysTab:CreateButton({
   Name = "Jeff The Killer Plushy",
   Callback = function()
    local tool = game:GetObjects("rbxassetid://13069619857")[1]
      tool.Parent = game.Players.LocalPlayer.Backpack
   end,
})

local ItemsTab = Window:CreateTab("Items" , "book") -- Title, Image
local ItemsSection = ItemsTab:CreateSection("Items")

local Button = ItemsTab:CreateButton({
   Name = "Mischievous Gummy Flashlight",
   Callback = function()
loadstring(game:HttpGet('https://github.com/Matthew201322/Doors-Scriptee/blob/Shakelights/Mischievous%20Shakelight.rbxm?raw=true'))()
   end,
})

  local Button = ItemsTab:CreateButton({
   Name = "Curious Gummy Flashlight",
   Callback = function()
  loadstring(game:HttpGet(("https://github.com/Matthew201322/Doors-Scriptee/blob/Shakelights/Curious%20Shakelight.rbxm?raw=true"))()
   end,
})

  local Button = ItemsTab:CreateButton({
   Name = "Guiding Gummy Flashlight",
   Callback = function()
  loadstring(game:HttpGet(("https://github.com/Matthew201322/Doors-Scriptee/blob/main/Guiding%20Shakelight.rbxm?raw=true"))()
   end,
})

  local Button = ItemsTab:CreateButton({
   Name = "Golden Gummy Flashlight",
   Callback = function()
  loadstring(game:HttpGet(("https://raw.githubusercontent.com/aadyian9000/the-thing/main/GoldenGummyFlashlight.lua"),true))()
   end,
})

local Button = ItemsTab:CreateButton({
   Name = "Resizer Stick",
   Callback = function()
loadstring(game:HttpGet('https://gist.githubusercontent.com/IdkMyNameLoll/f0178af2301ca90c09895f10f3e7bd4b/raw/46899ccc3626f3485d85f990012f7ef37ae52e5e/resizerDoorsRemake'))()
   end,
})

local Button = ItemsTab:CreateButton({
   Name = "NVCS-3000 ++ [Original]",
   Callback = function()
       _G.scanner_fps = 30
      _G.disable_static = false
      loadstring(game:HttpGet("https://raw.githubusercontent.com/notpoiu/Scripts/main/Scanner.lua"))()
   end,
})

local Button = ItemsTab:CreateButton({
   Name = "NVCS-3000 [Pink + 120FPS]",
   Callback = function()
  loadstring(Game:HttpGet("https://raw.githubusercontent.com/yieviro92creepy/WeirdPinktablet/main/sigma"))()
   end,
})

local Button = ItemsTab:CreateButton({
   Name = "NVCS-3000 [Gold + 30FPS]",
   Callback = function()
       _G.scanner_fps = 30
      _G.disable_static = false
      loadstring(game:HttpGet("https://pastebin.com/raw/umRteEPy"))()
   end,
})

local Button = ItemsTab:CreateButton({
   Name = "NVCS-3000 [Red + 300FPS]",
   Callback = function()
       _G.scanner_fps = 30
      _G.disable_static = false
      loadstring(game:HttpGet("https://pastebin.com/iBBqfYzn"))()
   end,
})

local Button = ItemsTab:CreateButton({
   Name = "NVCS-3000 [Grass]",
   Callback = function()
       _G.scanner_fps = 30
      _G.disable_static = false
      loadstring(game:HttpGet("https://raw.githubusercontent.com/Matthew201322/Doors-Scriptee/refs/heads/main/grass%20tablet.lua"))()
   end,
})

  local Button = ItemsTab:CreateButton({
   Name = "Bottle of Moon Light",
   Callback = function()
  loadstring(game:HttpGet('https://gist.githubusercontent.com/IdkMyNameLoll/04d7dd5e02688624b958b8c2604b924c/raw/9e86b34249f44ed2dd433176e67daaf3db30cde8/MoonBottle'))()
   end,
})

  local Button = ItemsTab:CreateButton({
   Name = "Bottle of Spiral Light",
   Callback = function()
  loadstring(game:HttpGet('https://gist.githubusercontent.com/IdkMyNameLoll/8b05c837bea9effac2554340465b4be1/raw/3f3be0ee72e7f153db39a16a40fa63dce6cde72d/SpiralBottle'))()
   end,
})

   local Button = ItemsTab:CreateButton({
   Name = "Star Jug",
   Callback = function()
loadstring(game:HttpGet("https://raw.githubusercontent.com/notpoiu/Scripts/refs/heads/main/StarJug.lua"))()
   end,
})

local Button = ItemsTab:CreateButton({
   Name = "BlackHole",
   Callback = function()
   loadstring(game:HttpGet("https://raw.githubusercontent.com/iimateiYT/Scripts/main/Black%20Hole.lua"))()
   end,
})

local Button = ItemsTab:CreateButton({
   Name = "Paintball Gun",
   Callback = function()
   loadstring(game:HttpGet("https://raw.githubusercontent.com/iimateiYT/Scripts/main/Paintball%20Gun.lua"))()
   end,
})

local Button = ItemsTab:CreateButton({
   Name = "Helpful Kiwi Bird",
   Callback = function()
   loadstring(game:HttpGet("https://pastebin.com/raw/PFERptU5", true))()
   end,
})

local Button = ItemsTab:CreateButton({
   Name = "Shears on Anthing",
   Callback = function()
   loadstring(game:HttpGet("https://raw.githubusercontent.com/MrNeRD0/Doors-Hack/main/shears_done.lua"))();
   end,
})

local Button = ItemsTab:CreateButton({
   Name = "Magnet script",
   Callback = function()
  loadstring(game:HttpGet("https://raw.githubusercontent.com/MrNeRD0/Doors-Hack/main/MagnetByNerd.lua"))()
   end,
})

local Button = ItemsTab:CreateButton({
   Name = "Seek Gun",
   Callback = function()
   loadstring(game:HttpGet("https://raw.githubusercontent.com/notpoiu/Scripts/main/seekgun.lua"))()
   end,
})

local Button = ItemsTab:CreateButton({
   Name = "Fortnite Rocket Launcher",
   Callback = function()
   loadstring(game:HttpGet("https://raw.githubusercontent.com/notpoiu/Scripts/main/rocketLauncher.lua"))()
   end,
})

local Button = ItemsTab:CreateButton({
   Name = "Grenade on everything",
   Callback = function()
   loadstring(game:HttpGet("https://pastebin.com/raw/zeFBYYy9", true))()
   end,
})

local Button = ItemsTab:CreateButton({
   Name = "Holy Grenade on everything",
   Callback = function()
   loadstring(game:HttpGet("https://pastebin.com/raw/x0YVrBkd", true))()
   end,
})

local SpawnsTab = Window:CreateTab("Spawns", 11372950109) -- Title, Image
local SpawnsSection = SpawnsTab:CreateSection("Spawns")

local Button = SpawnsTab:CreateButton({
   Name = "True INF Crucifix Guiding Light [Penguin Maniack]",
   Callback = function()
  _G.Uses = 414141414141
  _G.Range = 30
  _G.OnAnything = true
  _G.Fail = false
  _G.Variant = "Electric"
  loadstring(game:HttpGet('https://raw.githubusercontent.com/PenguinManiack/Crucifix/main/Crucifix.lua'))()
   end,
})

local Button = SpawnsTab:CreateButton({
   Name = "False INF Crucifix Guiding Light [Penguin Maniack]",
   Callback = function()
  _G.Uses = 414141414141
  _G.Range = 30
  _G.OnAnything = true
  _G.Fail = true
  _G.Variant = "Electric"
  loadstring(game:HttpGet('https://raw.githubusercontent.com/PenguinManiack/Crucifix/main/Crucifix.lua'))()
   end,
})

local Button = SpawnsTab:CreateButton({
   Name = "INF X Example Crucifix",
   Callback = function()
   ---====== Load module ======---

local module = loadstring(game:HttpGet("https://raw.githubusercontent.com/RegularVynixu/Utilities/refs/heads/main/Doors/Crucifix%20Everything/Source.lua"))()

---====== Create crucifix ======---

module.GiveCrucifix({
    Type = 1,
    Uses = 1000, -- nil : infinite uses
    Resist = false,
    EntitiesOnly = true, -- true : custom entities only
    IgnoreList = {}
})

--[[

CRUCIFIX TYPES:
-> 1: Guiding Light


COMING SOON:
-> Curious Light crucifix type

]]--
   end,
})

local Button = SpawnsTab:CreateButton({
   Name = "Rush [Killable]",
   Callback = function()
     ---====== Load spawner ======---

local spawner = loadstring(game:HttpGet("https://raw.githubusercontent.com/RegularVynixu/Utilities/main/Doors/Entity%20Spawner/V2/Source.lua"))()

---====== Create entity ======---

local entity = spawner.Create({
	Entity = {
		Name = "Template Entity",
		Asset = "https://github.com/RegularVynixu/Utilities/raw/main/Doors/Entity%20Spawner/Assets/Entities/Rush.rbxm",
		HeightOffset = 0
	},
	Lights = {
		Flicker = {
			Enabled = true,
			Duration = 1
		},
		Shatter = true,
		Repair = false
	},
	Earthquake = {
		Enabled = false
	},
	CameraShake = {
		Enabled = true,
		Range = 100,
		Values = {1.5, 20, 0.1, 1} -- Magnitude, Roughness, FadeIn, FadeOut
	},
	Movement = {
		Speed = 100,
		Delay = 2,
		Reversed = false
	},
	Rebounding = {
		Enabled = false,
		Type = "Blitz", -- "Blitz"
		Min = 1,
		Max = 1,
		Delay = 2
	},
	Damage = {
		Enabled = true,
		Range = 40,
		Amount = 125
	},
	Crucifixion = {
		Enabled = true,
		Range = 40,
		Resist = false,
		Break = true
	},
	Death = {
		Type = "Guiding", -- "Curious"
		Hints = {"Death", "Hints", "Go", "Here"},
		Cause = ""
	}
})

---====== Debug entity ======---

entity:SetCallback("OnSpawned", function()
    print("Entity has spawned")
end)

entity:SetCallback("OnStartMoving", function()
    print("Entity has started moving")
end)

entity:SetCallback("OnEnterRoom", function(room, firstTime)
    if firstTime == true then
        print("Entity has entered room: ".. room.Name.. " for the first time")
    else
        print("Entity has entered room: ".. room.Name.. " again")
    end
end)

entity:SetCallback("OnLookAt", function(lineOfSight)
	if lineOfSight == true then
		print("Player is looking at entity")
	else
		print("Player view is obstructed by something")
	end
end)

entity:SetCallback("OnRebounding", function(startOfRebound)
    if startOfRebound == true then
        print("Entity has started rebounding")
	else
        print("Entity has finished rebounding")
	end
end)

entity:SetCallback("OnDespawning", function()
    print("Entity is despawning")
end)

entity:SetCallback("OnDespawned", function()
    print("Entity has despawned")
end)

entity:SetCallback("OnDamagePlayer", function(newHealth)
	if newHealth == 0 then
		print("Entity has killed the player")
	else
		print("Entity has damaged the player")
	end
end)

--[[

DEVELOPER NOTE:
By overwriting 'CrucifixionOverwrite' the default crucifixion callback will be replaced with your custom callback.

entity:SetCallback("CrucifixionOverwrite", function()
    print("Custom crucifixion callback")
end)

]]--

---====== Run entity ======---

entity:Run()
        end,
})



local Button = SpawnsTab:CreateButton({
   Name = "Ambush",
   Callback = function()

        end,
})

local Button = SpawnsTab:CreateButton({
   Name = "Blitz [Killable]",
   Callback = function()
        ---====== Load spawner ======---

local spawner = loadstring(game:HttpGet("https://raw.githubusercontent.com/RegularVynixu/Utilities/main/Doors/Entity%20Spawner/V2/Source.lua"))()

---====== Create entity ======---

local entity = spawner.Create({
	Entity = {
		Name = "Blitz Example",
		Asset = "https://github.com/RegularVynixu/Utilities/raw/main/Doors/Entity%20Spawner/Assets/Entities/BackdoorRush.rbxm",
		HeightOffset = 0
	},
	Lights = {
		Flicker = {
			Enabled = true,
			Duration = 1
		},
		Shatter = true,
		Repair = false
	},
	Earthquake = {
		Enabled = false
	},
	CameraShake = {
		Enabled = true,
		Range = 100,
		Values = {1.5, 20, 0.1, 1}
	},
	Movement = {
		Speed = 100,
		Delay = 2,
		Reversed = false
	},
	Rebounding = {
		Enabled = true,
		Type = "Blitz",
		Min = 1,
		Max = math.random(1, 2),
		Delay = math.random(10, 30) / 10
	},
	Damage = {
		Enabled = true,
		Range = 40,
		Amount = 125
	},
	Crucifixion = {
		Enabled = true,
		Range = 40,
		Resist = false,
		Break = true
	},
	Death = {
		Type = "Curious",
		Hints = {"Oh... Hello.", "I didn't expect to see you here.", "Let's see what you died to.", "Oh, one of my favorites.", "She said we should call that one Blitz.", "Well... I'll see you later, right? You'll come back?", "Haha... of course you will fukin nigger."},
		Cause = ""
	}
})

---====== Debug entity ======---

entity:SetCallback("OnRebounding", function(startOfRebound)
	-- Variables for the entity
	local entityModel = entity.Model
	local main = entityModel:WaitForChild("Main")
	local attachment = main:WaitForChild("Attachment")
	local AttachmentSwitch = main:WaitForChild("AttachmentSwitch")
	local sounds = {
		footsteps = main:WaitForChild("Footsteps"),
		playSound = main:WaitForChild("PlaySound"),
		switch = main:WaitForChild("Switch"),
		switchBack = main:WaitForChild("SwitchBack")
	}

	-- Toggle particle emitters and lights within the entityModel
	-- To switch between green & red state
	for _, c in attachment:GetChildren() do
		c.Enabled = (not startOfRebound)
	end
	for _, c in AttachmentSwitch:GetChildren() do
		c.Enabled = startOfRebound
	end

	-- Play sounds
	if startOfRebound == true then
		sounds.footsteps.PlaybackSpeed = 0.35
		sounds.playSound.PlaybackSpeed = 0.25
		sounds.switch:Play()
	else
		sounds.footsteps.PlaybackSpeed = 0.25
		sounds.playSound.PlaybackSpeed = 0.16
		sounds.switchBack:Play()
	end
end)

---====== Run entity ======---

entity:Run()

        end,
})

local Button = SpawnsTab:CreateButton({
   Name = "A-60",
   Callback = function()
    loadstring(game:HttpGet("https://raw.githubusercontent.com/Idk-lol2/a-60aa/refs/heads/main/---%3D%3D%3D%3D%3D%3D%20a-60%20spawn%20%3D%3D%3D%3D%3D%3D---.txt"))() 
        end,
})

   local Button = SpawnsTab:CreateButton({
   Name = "Giggle",
   Callback = function()
getgenv().damage = 8 -- Default: 8
getgenv().minRadius = -20 -- Default: -20
getgenv().maxRadius = 20 -- Default: 20
getgenv().ragdollDissapears = true -- Default: true

loadstring(game:HttpGet("https://raw.githubusercontent.com/DripCapybara/Test/main/Doors/GiggleSpawn.lua"))()
   end,
})

local Button = SpawnsTab:CreateButton({
   Name = "Grumble",
   Callback = function()
-- Q TO SPAWN

local Speed = 12

local Players = game:GetService("Players")
local RunService = game:GetService("RunService")
local Debris = game:GetService("Debris")
local UserInputService = game:GetService("UserInputService")

local Player = Players.LocalPlayer
local Character = Player.Character or Player.CharacterAdded:Wait()

local Sword = game:GetObjects("rbxassetid://72674416931709")[1]

local Cache = game:GetObjects("rbxassetid://96223289630255")[1]
local Cache2 = game:GetObjects("rbxassetid://103869039972033")[1]

Cache:Destroy()
Cache2:Destroy()

Sword.Parent = Player.Backpack

task.spawn(function()
	local Tool = Sword
	local Handle = Tool:WaitForChild("Handle")
	local Humanoid = Character.Humanoid
	local Torso = Character:FindFirstChild("Torso") or Character:FindFirstChild("HumanoidRootPart")

	local function Create(ty)
		return function(data)
			local obj = Instance.new(ty)
			for k, v in pairs(data) do
				if type(k) == 'number' then
					v.Parent = obj
				else
					obj[k] = v
				end
			end
			return obj
		end
	end

	local BaseUrl = "rbxassetid://"

	local DamageValues = {
		BaseDamage = 5,
		SlashDamage = 10,
		LungeDamage = 30
	}

	local Animations = {
		R15Slash = 522635514,
		R15Lunge = 522638767
	}

	local Damage = DamageValues.BaseDamage

	local Grips = {
		Up = CFrame.new(0, 0, -1.70000005, 0, 0, 1, 1, 0, 0, 0, 1, 0),
		Out = CFrame.new(0, 0, -1.70000005, 0, 1, 0, 1, -0, 0, 0, 0, -1)
	}

	local Sounds = {
		Slash = Handle:WaitForChild("SwordSlash"),
		Lunge = Handle:WaitForChild("SwordLunge"),
		Unsheath = Handle:WaitForChild("Unsheath")
	}

	local ToolEquipped = false

	Tool.Grip = Grips.Up
	Tool.Enabled = true

	local function IsTeamMate(Player1, Player2)
		return (Player1 and Player2 and not Player1.Neutral and not Player2.Neutral and Player1.TeamColor == Player2.TeamColor)
	end

	local function TagHumanoid(humanoid, player)
		local Creator_Tag = Instance.new("ObjectValue")
		Creator_Tag.Name = "creator"
		Creator_Tag.Value = player
		Debris:AddItem(Creator_Tag, 2)
		Creator_Tag.Parent = humanoid
	end

	local function UntagHumanoid(humanoid)
		for i, v in pairs(humanoid:GetChildren()) do
			if v:IsA("ObjectValue") and v.Name == "creator" then
				v:Destroy()
			end
		end
	end

	local function CheckIfAlive()
		return (((Player and Player.Parent and Character and Character.Parent and Humanoid and Humanoid.Parent and Humanoid.Health > 0 and Torso and Torso.Parent) and true) or false)
	end

	local function Blow(Hit)
		if not Hit or not Hit.Parent or not CheckIfAlive() or not ToolEquipped then
			return
		end
		local RightArm = Character:FindFirstChild("Right Arm") or Character:FindFirstChild("RightHand")
		if not RightArm then
			return
		end
		local RightGrip = RightArm:FindFirstChild("RightGrip")
		if not RightGrip or (RightGrip.Part0 ~= Handle and RightGrip.Part1 ~= Handle) then
			return
		end
		local character = Hit.Parent
		if character == Character then
			return
		end
		local humanoid = character:FindFirstChildOfClass("Humanoid")
		if not humanoid or humanoid.Health == 0 then
			return
		end
		local player = Players:GetPlayerFromCharacter(character)
		if player and (player == Player or IsTeamMate(Player, player)) then
			return
		end
		UntagHumanoid(humanoid)
		TagHumanoid(humanoid, Player)
		humanoid:TakeDamage(Damage)	
	end

	local function Attack()
		Damage = DamageValues.SlashDamage
		Sounds.Slash:Play()

		if Humanoid then
			if Humanoid.RigType == Enum.HumanoidRigType.R6 then
				local Anim = Instance.new("StringValue")
				Anim.Name = "toolanim"
				Anim.Value = "Slash"
				Anim.Parent = Tool
			elseif Humanoid.RigType == Enum.HumanoidRigType.R15 then
				local Anim = Tool:FindFirstChild("R15Slash")
				if Anim then
					local Track = Humanoid:LoadAnimation(Anim)
					Track:Play(0)
				end
			end
		end	
	end

	local function Lunge()
		Damage = DamageValues.LungeDamage

		Sounds.Lunge:Play()

		if Humanoid then
			if Humanoid.RigType == Enum.HumanoidRigType.R6 then
				local Anim = Instance.new("StringValue")
				Anim.Name = "toolanim"
				Anim.Value = "Lunge"
				Anim.Parent = Tool
			elseif Humanoid.RigType == Enum.HumanoidRigType.R15 then
				local Anim = Tool:FindFirstChild("R15Lunge")
				if Anim then
					local Track = Humanoid:LoadAnimation(Anim)
					Track:Play(0)
				end
			end
		end	

		wait(0.2)
		Tool.Grip = Grips.Out
		wait(0.6)
		Tool.Grip = Grips.Up

		Damage = DamageValues.SlashDamage
	end

	Tool.Enabled = true
	local LastAttack = 0

	local function Activated()
		if not Tool.Enabled or not ToolEquipped or not CheckIfAlive() then
			return
		end
		Tool.Enabled = false
		local Tick = RunService.Stepped:wait()
		if (Tick - LastAttack < 0.2) then
			Lunge()
		else
			Attack()
		end
		LastAttack = Tick
		Damage = DamageValues.BaseDamage
		local SlashAnim = (Tool:FindFirstChild("R15Slash") or Create("Animation"){
			Name = "R15Slash",
			AnimationId = BaseUrl .. Animations.R15Slash,
			Parent = Tool
		})

		local LungeAnim = (Tool:FindFirstChild("R15Lunge") or Create("Animation"){
			Name = "R15Lunge",
			AnimationId = BaseUrl .. Animations.R15Lunge,
			Parent = Tool
		})
		Tool.Enabled = true
	end

	local function Equipped()
		if not CheckIfAlive() then
			return
		end
		ToolEquipped = true
		Sounds.Unsheath:Play()
	end

	local function Unequipped()
		Tool.Grip = Grips.Up
		ToolEquipped = false
	end

	Tool.Activated:Connect(Activated)
	Tool.Equipped:Connect(Equipped)
	Tool.Unequipped:Connect(Unequipped)

	Handle.Touched:Connect(Blow)
end)

UserInputService.InputBegan:Connect(function(input, gP)
	if input.KeyCode == Enum.KeyCode.Q and not gP then
		local Dummy = game:GetObjects("rbxassetid://96223289630255")[1]
		local Grumbo = game:GetObjects("rbxassetid://103869039972033")[1]

		Dummy.Parent = workspace
		Grumbo.Parent = workspace

		Dummy.HumanoidRootPart.CFrame = Character.HumanoidRootPart.CFrame + Vector3.new(math.random(-15, 15), 0, math.random(-15, 15))

		task.wait()

		local Idle = Grumbo.GrumbleRig.AnimationController.Animator:LoadAnimation(Grumbo.GrumbleRig.Idle)
		Idle.Looped = true
		Idle:Play()

		local Blink = Grumbo.GrumbleRig.AnimationController.Animator:LoadAnimation(Grumbo.GrumbleRig.Blink)

		local Stun = Grumbo.GrumbleRig.AnimationController.Animator:LoadAnimation(Grumbo.GrumbleRig.Stun)

		task.spawn(function()
			while Grumbo:IsDescendantOf(workspace) do
				task.wait(math.random(2, 5))
				Blink:Play()
			end
		end)

		local function followPlayer()
			local Direction = (Character.HumanoidRootPart.Position - Dummy.HumanoidRootPart.Position).unit
			Dummy.HumanoidRootPart.Velocity = Direction * Speed
			Dummy.HumanoidRootPart.CFrame = CFrame.new(Dummy.HumanoidRootPart.Position, Character.HumanoidRootPart.Position)
		end

		Dummy.Humanoid:GetPropertyChangedSignal("Health"):Connect(function()
			if Dummy.Humanoid.Health <= 0 then
				Stun:Play()
				task.wait(1)
				Dummy:Destroy()
				Grumbo:Destroy()
			end
		end)

		RunService.RenderStepped:Connect(function()
			if Grumbo:IsDescendantOf(workspace) and Dummy:IsDescendantOf(workspace) and Dummy:FindFirstChild("HumanoidRootPart") and Dummy:FindFirstChild("Humanoid").Health > 0 then
				local Distance = (Character.HumanoidRootPart.Position - Dummy.HumanoidRootPart.Position).magnitude

				if Distance <= math.huge then
					followPlayer()
				end

				Grumbo:PivotTo(Dummy.HumanoidRootPart.CFrame)
			end
		end)
	end
end)
        end,
})

local Button = SpawnsTab:CreateButton({
   Name = "Glitch",
   Callback = function()
     local Data = require(game.Players.LocalPlayer.PlayerGui.MainUI.Initiator.Main_Game)
        require(game.ReplicatedStorage.ClientModules.EntityModules.Glitch).stuff(Data, workspace.CurrentRooms[tostring(game.ReplicatedStorage.GameData.LatestRoom.Value)])
        end,
})

local Button = SpawnsTab:CreateButton({
   Name = "Halt",
   Callback = function()
    require(game.ReplicatedStorage.ClientModules.EntityModules.Shade).stuff(require(game.Players.LocalPlayer.PlayerGui.MainUI.Initiator.Main_Game),
workspace.CurrentRooms[game.Players.LocalPlayer:GetAttribute("CurrentRoom")])
        end,
})

local Button = SpawnsTab:CreateButton({
   Name = "100 screechs",
   Callback = function()
     local Data = require(game.Players.LocalPlayer.PlayerGui.MainUI.Initiator.Main_Game)

    for i = 1, 100 do -- Will run the script 100 times
    coroutine.wrap(function() require(game.Players.LocalPlayer.PlayerGui.MainUI.Initiator.Main_Game.RemoteListener.Modules.Screech)(Data) end)()
    end

        end,
})

local Button = SpawnsTab:CreateButton({
   Name = "Screech",
   Callback = function()
     require(game.StarterGui.MainUI.Initiator.Main_Game.RemoteListener.Modules.Screech)(require(game.Players.LocalPlayer.PlayerGui.MainUI.Initiator.Main_Game),
    workspace.CurrentRooms[game.Players.LocalPlayer:GetAttribute("CurrentRoom")])
        end,
})

local Button = SpawnsTab:CreateButton({
   Name = "Timothy",
   Callback = function()
    local a = game.Players.LocalPlayer.PlayerGui.MainUI.Initiator.Main_Game
require(a.RemoteListener.Modules.SpiderJumpscare)(require(a), workspace.CurrentRooms["0"].Assets.Dresser.DrawerContainer, 0.2)
        end,
})

local Button = SpawnsTab:CreateButton({
   Name = "Seek eyes",
   Callback = function()
             local Data = require(game.Players.LocalPlayer.PlayerGui.MainUI.Initiator.Main_Game)
        require(game:GetService("ReplicatedStorage").ClientModules.EntityModules.Seek).tease(nil, workspace.CurrentRooms:WaitForChild(game.ReplicatedStorage.GameData.LatestRoom.Value), 14, 1665596753, true)
        end,
})

local Button = SpawnsTab:CreateButton({
   Name = "Bloodroom Jack",
   Callback = function()
             local v1 = require(game.ReplicatedStorage.ClientModules.Module_Events)
        local room = workspace.CurrentRooms[game.Players.LocalPlayer:GetAttribute("CurrentRoom")]
        local seconds = 1000000
        v1.tryp(workspace.CurrentRooms[game.Players.LocalPlayer:GetAttribute("CurrentRoom")], seconds)
        end,
})

local Button = SpawnsTab:CreateButton({
   Name = "Trollface [Killable]",
   Callback = function()
     loadstring(game:HttpGet("https://api.hugebonus.xyz/scripts/TrollFaceSpawner.lua"))()   
        end,
})

local ConfigTab = Window:CreateTab("Config", "github")
local ConfigSection = ConfigTab:CreateSection("Config")

local Button = ConfigTab:CreateButton({
   Name = "Infinite X Yeild",
   Callback = function()
       loadstring(game:HttpGet(('https://raw.githubusercontent.com/EdgeIY/infiniteyield/master/source'),true))()
        end,
})

local Button = ConfigTab:CreateButton({
   Name = "MSpaint",
   Callback = function()
       loadstring(game:HttpGet("https://raw.githubusercontent.com/notpoiu/mspaint/main/main.lua"))()
        end,
})

local Button = ConfigTab:CreateButton({
   Name = "Lolhax V3 Beta",
   Callback = function()
       loadstring(game:HttpGet("https://raw.githubusercontent.com/Robloxexploiterz/Release-Lolhax/refs/heads/main/LX%20Doors%20v3.lua"))()
        end,
})

local Button = ConfigTab:CreateButton({
   Name = "Destroy Inteferance",
   Callback = function()
       Rayfield:Destroy()
        end,
})
