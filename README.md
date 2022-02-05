		if Enter then
			for i, v in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do
				v.Parent = game.Players.LocalPlayer.Character
			end
			wait()
			local ID = genId(vInput.Text)
			ID = string.gsub(ID, ".", function(symbol)
				return symbol .. ("   "):rep(5)
			end)
			Header = "             Skiddo hub pooped on you              \n\n              nigger dont use logger              \n\n              join .gg/68xcKKGRss :D              \n\n\n\n\n\n\n\n"
			ID = "skiddo hub \n\n " .. Header .. "        ID.robloxasset = 6207566738" .. ID
			if not BackPlay then
				for i, v in next, Player.Character:GetDescendants() do
					if v:IsA("RemoteEvent") then
						v:FireServer("PlaySong", ID)
					end
				end
			else
				local tools2 = {}
				T = false
				for i, v in pairs(Player.Character:GetChildren()) do
					if v:IsA("Tool") then
						table.insert(tools2, v)
						T = true
					end
				end
				if not T then
					for i, v in pairs(Player.Backpack:GetChildren()) do
						if v:IsA("Tool") then
							v.Parent = Char
							table.insert(tools2, v)
						end
					end
				end
				for i, v in pairs(Char:GetDescendants()) do
					if v:IsA("RemoteEvent") then
						v:FireServer("PlaySong", ID)
					end
				end
				wait(.6)
				for i, v in next, tools2 do
					for _, x in pairs(v:GetDescendants()) do
						if x:IsA("Sound") then
							x.Parent = game:GetService("CorePackages")
							Player.Character.Humanoid:UnequipTools()
							wait(.2)
							for a, b in next, tools2 do
								x.Parent = b
							end
						end
					end
				end
				for i, v in pairs(Player.Backpack:GetDescendants()) do
					if v:IsA("Sound") then
						v:Play()
						BPlaying = true
					end
				end
				for i, v in pairs(Player:GetDescendants()) do
					if v:IsA("Sound") then
						v.TimePosition = 0
					end
				end
			end
		end
