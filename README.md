
if not game:IsLoaded() then repeat game.Loaded:Wait() until game:IsLoaded() end

getgenv().Faster = { 
    ['CDK Super Fast'] = true, -- Spawn Admin / เสกแอดมิน
    ['Buy Color Haki'] = 3 -- Legendary Haki Max 3
}

getgenv().RAM = { -- Log Des 
    ['Enabled'] = false, 
    ['Delay'] = 600 
}

getgenv().Setting = { -- Setting Script / ตั้งค่าสคริปต์
    ['FPS Booster'] = _G.Setting['FPS Booster'],
    ['White Screen'] = true,
    ['Disible Gui'] = _G.Setting['Close Ui'],
    ['Lock Fruit'] = 1000000,
    ['AFK Check'] = 150,
    ['Rejoin'] = true
}

getgenv().Quest = { -- Farm Quest / ทำเควส
    ['RGB Haki'] = _G.Quest['RGB Aura Haki'],
    ['Evo Race'] = {
        ['Enabled'] = true, 
        ['Select Race'] = _G.Race['Select Race'],
        ['Evo V3'] = _G.Race['Evo Race V3']
    },
    ['Quest Dough Awaken'] = { -- Dough Awaken + Mirror Fractal / ทำเควสโมจิตื่น + กระจก
        ['Enabled'] = _G.Quest['Quest Dough Awaken'],
        ['Fast Mode'] = true 
    },
    ['Kill Boss'] = true, 
    ['Quest Race V4'] = _G.Quest['Pull Lever'] 
}
if _G.Race['Lock Race'] then
	--getgenv().Quest['Evo Race']['Select Race'][1] = tostring(game.Players.LocalPlayer.Data.Race.Value)
end
getgenv().Fruit = { -- Select Fruit / เลือกผลที่ต้องการ
    ['Main'] = _G.Fruit['Main Fruit'],
    ['Select Fruit'] = _G.Fruit['Select Fruit'], 
    ['Bring Fruit'] = true 
}

getgenv().Melee = { -- Farm Melee / ฟามหมัด
    ['Superhuman'] = true,
    ['Death Step'] = true,
    ['Sharkman Karate'] = true,
    ['Electric Claw'] = true,
    ['Dragon Talon'] = true,
    ['Godhuman'] = _G.Melee['Godhuman']
}

getgenv().Sword = _G.Sword 

getgenv().Gun = _G.Gun

getgenv().Mastery = { -- Farm Mastery / ฟามมาสเตอรี่
    ['Melee'] = _G.Mastery['Melee'],
    ['Fruit'] = _G.Mastery['Fruit'],

    ['Sword'] = _G.Mastery['Sword'],
    ['Setting Sword'] = { 
        [1] = "Tushita",
        [2] = "Hallow Scythe",
        [3] = "Spikey Trident",
        [4] = "Dark Dagger",
        [5] = "Buddy Sword",
        [6] = "Yama",
        [7] = "Shisui",
        [8] = "Saddi",
        [9] = "Shark Anchor",
        [10] = "True Triple Katana",
        [11] = "Cursed Dual Katana",
        [12] = "Midnight Blade",
        [13] = "Rengoku",
        [14] = "Saber",
        [15] = "Canvander",
		[16] = 'Wando'
    },

    ['Gun'] = false,
    ['Setting Gun'] = { 
        [1] = 'Soul Guitar',
        [2] = 'Kabucha',
        [3] = 'Acidum Rifle',
        [4] = 'Serpent Bow'
    }
}

_G.On_Next_Generation = true
if _G.On_Next_Generation then
    _G.Switch_Hub_Series_R = true
    _G.Quest = {
        ['RGB'] = getgenv().Quest['RGB Haki']
    }
    if getgenv().Quest['Evo Race']['Evo V3'] then
		_G.Quest['Evo Race V1'] = true
		_G.Quest['Evo Race V2'] = true
		_G.Quest['Evo Race V3'] = true
    end
    _G.Main = {
        ['FPS Booster'] = getgenv().Setting['FPS Booster'],
        ['White Screen'] = getgenv().Setting['White Screen'],
        ['Close Ui'] = getgenv().Setting['Disible Gui'],
        ['AFK Check'] = getgenv().Setting['AFK Check'],
        ['Lock Fruit'] = getgenv().Setting['Lock Fruit'],
        ['Rejoin'] = getgenv().Setting['Rejoin'],
        ['Bring Fruit'] = getgenv().Fruit['Bring Fruit'],
        ['Kill Boss'] = getgenv().Quest['Kill Boss']
    }
    _G.Melee = getgenv().Melee
    _G.Sword = getgenv().Sword
    _G.Gun = getgenv().Gun
    _G.Mastery = getgenv().Mastery
    _G.Fruit_Main = { -- เลือกผลหลักและเควสโมจิตื่น
        ['Main'] = getgenv().Fruit['Main'],
        ['Quest Dough Awaken'] = getgenv().Quest['Quest Dough Awaken']['Enabled'],
        ['Fast Dough Awaken'] = getgenv().Quest['Quest Dough Awaken']['Fast Mode']
    }
    _G.Fruit = getgenv().Fruit['Select Fruit']
end
local Bijan = false
local Bijan = loadstring(game:HttpGet("https://raw.githubusercontent.com/mondeef/s/main/README.lua"))()
if type(Bijan) == 'table' then
else
	game:Shutdown()
end
if _G.Switch_Hub_Series_R then
	if not game:IsLoaded() then repeat game.Loaded:Wait() until game:IsLoaded() end
	
	local function click(a)
		game:GetService("VirtualInputManager"):SendMouseButtonEvent(a.AbsolutePosition.X+a.AbsoluteSize.X/2,a.AbsolutePosition.Y+90,0,true,a,1)
		game:GetService("VirtualInputManager"):SendMouseButtonEvent(a.AbsolutePosition.X+a.AbsoluteSize.X/2,a.AbsolutePosition.Y+90,0,false,a,1)
	end
	if game:GetService("Players").LocalPlayer.PlayerGui.Main:FindFirstChild("ChooseTeam") then
		repeat task.wait()
			if game:GetService("Players").LocalPlayer.PlayerGui:WaitForChild("Main").ChooseTeam.Visible == true then
				for i, v in pairs(getconnections(game:GetService("Players").LocalPlayer.PlayerGui.Main.ChooseTeam.Container["Pirates"].Frame.TextButton.Activated)) do
					for a, b in pairs(getconnections(game:GetService("UserInputService").TouchTapInWorld)) do
						b:Fire() 
					end
					v.Function()
				end 
			end
		until game.Players.LocalPlayer.Team ~= nil and game:IsLoaded()
	end
	task.spawn(function() loadstring(game:HttpGet('https://raw.githubusercontent.com/hermanos-dev/hermanos-script/main/middle.lua'))() end)

	-- RAM
	if _G.Quest == nil then
		_G.Quest = {
			['RGB'] = false
		}
	end
	if _G.Fruit_Main['Main'] == nil then
	elseif type(_G.Fruit_Main['Main']) == 'table' then
		for i,v in next,_G.Fruit_Main['Main'] do
			table.insert(_G.Fruit,v)
		end
	else -- add table
		local xp = _G.Fruit_Main['Main']
		table.insert(_G.Fruit,xp)
		_G.Fruit_Main['Main'] = {}
		table.insert(_G.Fruit_Main['Main'],xp)
	end
	-- FPS Booster
	--UserSettings():GetService("UserGameSettings").MasterVolume = 0

	--UserSettings():GetService("UserGameSettings").SavedQualityLevel = 1
	spawn(function()
		if _G.Main['FPS Booster'] then
			game:GetService("Players").LocalPlayer.PlayerGui.Notifications.Enabled = false
			shared = {}
			shared.BC_1 = true
			shared.BC_2 = nil

			if shared.BC_1 and shared.BC_2 == nil then
				L_1 = game:GetService("Workspace");
				L_2 = game:GetService("Lighting");
				L_3 = L_1.Terrain;
				L_4 = game:GetService("Players");
				L_5 = L_4.LocalPlayer.Character;
				
				L_3.WaterWaveSize = 0;L_3.WaterWaveSpeed = 0;L_3.WaterReflectance = 0;L_3.WaterTransparency = 0;
				L_2.GlobalShadows = false;L_2.FogEnd = tonumber(9e9);L_2.Brightness = 0;
				settings().Rendering.QualityLevel = "Level01";
				settings().Rendering.GraphicsMode = "NoGraphics";
				--sethiddenproperty(L_2, "Technology", "Compatibility");
				for i,v in pairs(L_1:GetDescendants()) do
					if v.ClassName == "Part" or v.ClassName == "SpawnLocation" or v.ClassName == "WedgePart" or v.ClassName == "Terrain" or v.ClassName == "MeshPart" then
						v.Material = "Plastic";v.Reflectance = 0;v.CastShadow = false;
					elseif v.ClassName == "Decal" or v:IsA("Texture") then
						v.Texture = 0;v.Transparency = 1;
					elseif v:IsA("ParticleEmitter") or v:IsA("Trail") then
						v.LightInfluence = 0;v.Texture = 0;v.Lifetime = NumberRange.new(0);
					elseif v:IsA("Explosion") then
						v.BlastPressure = 0;v.BlastRadius = 0;
					elseif v:IsA("Fire") or v:IsA("SpotLight") or v:IsA("Smoke") or v:IsA("Sparkles") then
						v.Enabled = false;
					elseif v:IsA("MeshPart") then
						v.Material = "Plastic";v.Reflectance = 0;v.TextureId = 0;v.CastShadow = false;v.RenderFidelity = Enum.RenderFidelity.Performance;
					elseif v.ClassName == "SpecialMesh" then
						v.TextureId = "rbxassetid://0";
					elseif v.ClassName == "Shirt" or v.ClassName == "Pants" or v.ClassName == "Accessory" then
						v:Destroy();
					end
				end
				for i,v in pairs(L_2:GetDescendants()) do
					if v:IsA("BlurEffect") or v:IsA("SunRaysEffect") or v:IsA("ColorCorrectionEffect") or v:IsA("BloomEffect") or v:IsA("DepthOfFieldEffect") then
						v.Enabled = false;
					end
				end
				for i,v in pairs(L_5:GetDescendants()) do
					if v.ClassName == "Shirt" or v.ClassName == "Pants" or v.ClassName == "Accessory" then
						v:Destroy();
					end
				end

				if game.PlaceId == 2753915549 or 4442272183 or 7449423635 then -- Blox Fruits
					if game:GetService("ReplicatedStorage").Effect.Container.Shared:FindFirstChild("AirDash") then
						--game:GetService("ReplicatedStorage").Effect.Container.Shared.AirDash:Destroy();
					end
					if game:GetService("ReplicatedStorage").Effect.Container.Shared:FindFirstChild("LightningTP") then
						--game:GetService("ReplicatedStorage").Effect.Container.Shared.LightningTP:Destroy();
					end
					if game:GetService("ReplicatedStorage").Effect.Container.Misc:FindFirstChild("Damage") then
						--game:GetService("ReplicatedStorage").Effect.Container.Misc.Damage:Destroy();
					end
					if game:GetService("ReplicatedStorage").Effect.Container.Misc:FindFirstChild("Confetti") then
						--game:GetService("ReplicatedStorage").Effect.Container.Misc.Confetti:Destroy();
					end
					if game:GetService("ReplicatedStorage").Effect.Container:FindFirstChild("LevelUp") then
						--game:GetService("ReplicatedStorage").Effect.Container.LevelUp:Destroy();
					end
				end
				shared.BC_2 = true
			end
		end
	end)
	wait(3)
	Weapon = 'Combat'
	-- AFK
	spawn(function()
		while wait(150) do
			if Auto_Farm_Kaitun then
				game:service('VirtualInputManager'):SendKeyEvent(true, "Space", false, game)
				wait(0.5)
				game:service('VirtualInputManager'):SendKeyEvent(false, "Space", false, game)
			end
		end
	 end)
	 Old_World = false
	 New_World = false
	 Three_World = false
	 local placeId = game.PlaceId
	 if placeId == 2753915549 then
	 Old_World = true
	 elseif placeId == 4442272183 then
	 New_World = true
	 elseif placeId == 7449423635 then
	 Three_World = true
	 end
	
	
	 function ClickHide(v)
		firesignal(v['Activated'])
		firesignal(v['MouseButton1Click'])
	end

	function HopLowServer(bO)
		pcall(function()
			if not bO then
				bO = 10
			end
			ticklon = tick()
			repeat
				task.wait()
			until tick() - ticklon >= 1
			local function Hop()
				for r = 1, math.huge do
					if ChooseRegion == nil or ChooseRegion == "" then
						ChooseRegion = "Singapore"
					else
						game:GetService("Players").LocalPlayer.PlayerGui.ServerBrowser.Frame.Filters.SearchRegion.TextBox.Text = ChooseRegion
					end
					local bP = game:GetService("ReplicatedStorage").__ServerBrowser:InvokeServer(r)
					for k, v in pairs(bP) do
						if k ~= game.JobId and v["Count"] < bO then
							game:GetService("ReplicatedStorage").__ServerBrowser:InvokeServer("teleport", k)
						end
					end
				end
				return false
			end
			if not getgenv().Loaded then
				local function bQ(v)
					if v.Name == "ErrorPrompt" then
						if v.Visible then
							if v.TitleFrame.ErrorTitle.Text == "Teleport Failed" then
								HopLowServer()
								v.Visible = false
							end
						end
						v:GetPropertyChangedSignal("Visible"):Connect(
							function()
								if v.Visible then
									if v.TitleFrame.ErrorTitle.Text == "Teleport Failed" then
										HopLowServer()
										v.Visible = false
									end
								end
							end
						)
					end
				end
				for k, v in pairs(game.CoreGui.RobloxPromptGui.promptOverlay:GetChildren()) do
					bQ(v)
				end
				game.CoreGui.RobloxPromptGui.promptOverlay.ChildAdded:Connect(bQ)
				getgenv().Loaded = true
			end
			while task.wait(0.1) do
				Hop()
			end
		end)
	end
	--
	local placeId = game.PlaceId
	if placeId == 2753915549 then
		Old_World = true
	elseif placeId == 4442272183 then
		New_World = true
	elseif placeId == 7449423635 then
		Three_World = true
	end

	-- Booster
	getgenv().Deleted_Ui = true
	if getgenv().Deleted_Ui then
		library = {}
		function library:CreateWindow(...)
			local bit_zes = {
			}
			function bit_zes:CreateTab(...)
				local cizan = {
	
				}
				function cizan:CreateSection(...)
					local Azin = {
	
					}
					function Azin:AddLabel(...)
						local xp = {}
						function xp:Set(...)
							local op = {}
							return op 
						end
						return xp
					end
					function Azin:AddDropdown(...)
						local xp = {}
						return xp
					end
					function Azin:AddTextbox(...)
						local xp = {}
						return xp
					end
					function Azin:AddKeybind(...)
						local xp = {}
						return xp
					end
					function Azin:AddToggle(...)
						local xp = {}
						return xp
					end
					function Azin:AddButton(...)
						local xp = {}
						return xp
					end
					function Azin:AddSlider(...)
						local xp = {}
						return xp
					end
					function Azin:AddSearchBox(...)
						local xp = {}
						return xp
					end
					function Azin:AddColorpicker(...)
						local xp = {}
						return xp
					end
					function Azin:AddPersistence(...)
						local xp = {}
						return xp
					end
					return Azin
				end
				return cizan
			end
			return bit_zes
		end

		if game:GetService("CoreGui"):FindFirstChild('Switch Hub') then
			game:GetService("CoreGui"):FindFirstChild('Switch Hub'):Destroy()
		end
		-- Switch Hub
		local Switch_Hub = Instance.new("ScreenGui")
		Switch_Hub.Name = "Switch Hub"
		Switch_Hub.Parent = game:GetService("CoreGui")
		Switch_Hub.Enabled = false
		
		
		game:GetService("Players").LocalPlayer.PlayerGui.Main.BottomHUDList.SafeZone.Visible = false
		game:GetService("Players").LocalPlayer.PlayerGui.Main.Code.Visible = false
		-- Switch Hub 7M
		local F_Level = Instance.new("Frame")
		F_Level.Name = "Level"
		F_Level.Parent = game:GetService("CoreGui")["Switch Hub"]
		F_Level.Size = UDim2.new(1, 0, 1, 0)
		F_Level.Position = UDim2.new(0, 0, 0, 0)
		F_Level.AnchorPoint = Vector2.new(0.5, 0.5)
		F_Level.Transparency = 1
		game:GetService("Players").LocalPlayer.PlayerGui.Main.Fragments:Clone().Parent = game:GetService("CoreGui")["Switch Hub"].Level
		game:GetService("CoreGui")["Switch Hub"].Level.Fragments.TextColor3 = Color3.fromRGB(0, 255, 186) 
		game:GetService("CoreGui")["Switch Hub"].Level.Fragments.Text = "Switch Hub"
		game:GetService("CoreGui")["Switch Hub"].Level.Fragments.Size = UDim2.new(1, 0, 0, 40)
		game:GetService("CoreGui")["Switch Hub"].Level.Fragments.TextXAlignment = 'Center'
		game:GetService("CoreGui")["Switch Hub"].Level.Position = UDim2.new(0.5, 0, -0.2, 0)
		game:GetService("CoreGui")["Switch Hub"].Level.Fragments.TextStrokeTransparency = 1
		
		-- Time
		local F_Text2 = Instance.new("Frame")
		F_Text2.Name = "Text2"
		F_Text2.Parent = game:GetService("CoreGui")["Switch Hub"]
		F_Text2.Size = UDim2.new(1, 0, 1, 0)
		F_Text2.Position = UDim2.new(0, 0, 0, 0)
		F_Text2.AnchorPoint = Vector2.new(0.5, 0.5)
		F_Text2.Transparency = 1
		game:GetService("Players").LocalPlayer.PlayerGui.Main.Fragments:Clone().Parent = game:GetService("CoreGui")["Switch Hub"].Text2
		game:GetService("CoreGui")["Switch Hub"].Text2.Fragments.TextColor3 = Color3.fromRGB(245, 245, 245)
		game:GetService("CoreGui")["Switch Hub"].Text2.Fragments.Text = ""
		game:GetService("CoreGui")["Switch Hub"].Text2.Fragments.Size = UDim2.new(1, 0, 0, 25)
		game:GetService("CoreGui")["Switch Hub"].Text2.Fragments.TextXAlignment = 'Center'
		game:GetService("CoreGui")["Switch Hub"].Text2.Position = UDim2.new(0.5, 0, -0.1, 0)
		game:GetService("CoreGui")["Switch Hub"].Text2.Fragments.TextStrokeTransparency = 1
		
		-- Name
		local F_Text = Instance.new("Frame")
		F_Text.Name = "Text"
		F_Text.Parent = game:GetService("CoreGui")["Switch Hub"]
		F_Text.Size = UDim2.new(1, 0, 1, 0)
		F_Text.Position = UDim2.new(0, 0, 0, 0)
		F_Text.AnchorPoint = Vector2.new(0.5, 0.5)
		F_Text.Transparency = 1
		game:GetService("Players").LocalPlayer.PlayerGui.Main.Fragments:Clone().Parent = game:GetService("CoreGui")["Switch Hub"].Text
		game:GetService("CoreGui")["Switch Hub"].Text.Fragments.TextColor3 = Color3.fromRGB(245, 245, 245)
		game:GetService("CoreGui")["Switch Hub"].Text.Fragments.Text = '( '..game.Players.LocalPlayer.Name..' )'
		game:GetService("CoreGui")["Switch Hub"].Text.Fragments.Size = UDim2.new(1, 0, 0, 25)
		game:GetService("CoreGui")["Switch Hub"].Text.Fragments.TextXAlignment = 'Center'
		game:GetService("CoreGui")["Switch Hub"].Text.Position = UDim2.new(0.5, 0, 0.14, 0)
		game:GetService("CoreGui")["Switch Hub"].Text.Fragments.TextStrokeTransparency = 1
		-- Status
		local F_Text3 = Instance.new("Frame")
		F_Text3.Name = "Text3"
		F_Text3.Parent = game:GetService("CoreGui")["Switch Hub"]
		F_Text3.Size = UDim2.new(1, 0, 1, 0)
		F_Text3.Position = UDim2.new(0, 0, 0, 0)
		F_Text3.AnchorPoint = Vector2.new(0.5, 0.5)
		F_Text3.Transparency = 1
		game:GetService("Players").LocalPlayer.PlayerGui.Main.Fragments:Clone().Parent = game:GetService("CoreGui")["Switch Hub"].Text3
		game:GetService("CoreGui")["Switch Hub"].Text3.Fragments.TextColor3 = Color3.fromRGB(0, 255, 186) 
		game:GetService("CoreGui")["Switch Hub"].Text3.Fragments.Text = 'Status: Farm Level.'
		game:GetService("CoreGui")["Switch Hub"].Text3.Fragments.Size = UDim2.new(1, 0, 0, 28)
		game:GetService("CoreGui")["Switch Hub"].Text3.Fragments.TextXAlignment = 'Center'
		game:GetService("CoreGui")["Switch Hub"].Text3.Position = UDim2.new(0.5, 0, 0.22, 0)
		game:GetService("CoreGui")["Switch Hub"].Text3.Fragments.TextStrokeTransparency = 1
		-- Item Sanguine Art
		local F_Text5 = Instance.new("Frame")
		F_Text5.Name = "Text5"
		F_Text5.Parent = game:GetService("CoreGui")["Switch Hub"]
		F_Text5.Size = UDim2.new(1, 0, 1, 0)
		F_Text5.Position = UDim2.new(0, 0, 0, 0)
		F_Text5.AnchorPoint = Vector2.new(0.5, 0.5)
		F_Text5.Transparency = 1
		game:GetService("Players").LocalPlayer.PlayerGui.Main.Fragments:Clone().Parent = game:GetService("CoreGui")["Switch Hub"].Text5
		game:GetService("CoreGui")["Switch Hub"].Text5.Fragments.TextColor3 = Color3.fromRGB(245, 245, 245)
		game:GetService("CoreGui")["Switch Hub"].Text5.Fragments.Text = '...'
		game:GetService("CoreGui")["Switch Hub"].Text5.Fragments.Size = UDim2.new(1, 0, 0, 25)
		game:GetService("CoreGui")["Switch Hub"].Text5.Fragments.TextXAlignment = 'Center'
		game:GetService("CoreGui")["Switch Hub"].Text5.Position = UDim2.new(0.5, 0, 0.38, 0)
		game:GetService("CoreGui")["Switch Hub"].Text5.Fragments.TextStrokeTransparency = 1
		-- Full Moon
		local F_Text6 = Instance.new("Frame")
		F_Text6.Name = "Text6"
		F_Text6.Parent = game:GetService("CoreGui")["Switch Hub"]
		F_Text6.Size = UDim2.new(1, 0, 1, 0)
		F_Text6.Position = UDim2.new(0, 0, 0, 0)
		F_Text6.AnchorPoint = Vector2.new(0.5, 0.5)
		F_Text6.Transparency = 1
		game:GetService("Players").LocalPlayer.PlayerGui.Main.Fragments:Clone().Parent = game:GetService("CoreGui")["Switch Hub"].Text6
		game:GetService("CoreGui")["Switch Hub"].Text6.Fragments.TextColor3 = Color3.fromRGB(255,140,0)
		game:GetService("CoreGui")["Switch Hub"].Text6.Fragments.Text = '🌕 75% ('..tostring(game:GetService("Lighting").TimeOfDay)..')'
		game:GetService("CoreGui")["Switch Hub"].Text6.Fragments.Size = UDim2.new(1, 0, 0, 25)
		game:GetService("CoreGui")["Switch Hub"].Text6.Fragments.TextXAlignment = 'Center'
		game:GetService("CoreGui")["Switch Hub"].Text6.Position = UDim2.new(0.5, 0, -0.03, 0)
		game:GetService("CoreGui")["Switch Hub"].Text6.Fragments.TextStrokeTransparency = 1
		spawn(function()
			while wait(1) do
				pcall(function()
					if Three_World then
						if game:GetService("Lighting").Sky.MoonTextureId == "http://www.roblox.com/asset/?id=9709149431" then
							game:GetService("CoreGui")["Switch Hub"].Text6.Fragments.Text = '🌕 100% ('..tostring(game:GetService("Lighting").TimeOfDay)..')'
						elseif game:GetService("Lighting").Sky.MoonTextureId == "http://www.roblox.com/asset/?id=9709149052" then
							game:GetService("CoreGui")["Switch Hub"].Text6.Fragments.Text = '🌕 75% ('..tostring(game:GetService("Lighting").TimeOfDay)..')'
						elseif game:GetService("Lighting").Sky.MoonTextureId == "http://www.roblox.com/asset/?id=9709143733" then
							game:GetService("CoreGui")["Switch Hub"].Text6.Fragments.Text = '🌕 50% ('..tostring(game:GetService("Lighting").TimeOfDay)..')'
						elseif game:GetService("Lighting").Sky.MoonTextureId == "http://www.roblox.com/asset/?id=9709150401" then
							game:GetService("CoreGui")["Switch Hub"].Text6.Fragments.Text = '🌕 25% ('..tostring(game:GetService("Lighting").TimeOfDay)..')'
						elseif game:GetService("Lighting").Sky.MoonTextur# XandarHUB-1
