-- konozis hub: Fully Clean & Fixed Version
print("=== KONOZIS HUB LOADING ===")

local CoreGui = game:GetService("CoreGui")
local Players = game:GetService("Players")
local RunService = game:GetService("RunService")
local Lighting = game:GetService("Lighting")
local player = Players.LocalPlayer

-- Безопасный контейнер для обхода античита
local containerParent = gethui and gethui() or CoreGui

pcall(function()
	if containerParent:FindFirstChild("KonozisHubPro") then
		containerParent.KonozisHubPro:Destroy()
	end
end)

local Gui = Instance.new("ScreenGui")
Gui.Name = "KonozisHubPro"
Gui.ResetOnSpawn = false
Gui.IgnoreGuiInset = true
Gui.DisplayOrder = 2147483647
Gui.Parent = containerParent

-- 1. ИНТРО (5 секунд: черный фон + фиолетовый текст)
local IntroBg = Instance.new("Frame", Gui)
IntroBg.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
IntroBg.Size = UDim2.new(1, 0, 1, 0)
IntroBg.ZIndex = 999

local IntroText = Instance.new("TextLabel", IntroBg)
IntroText.BackgroundTransparency = 1
IntroText.Size = UDim2.new(1, 0, 1, 0)
IntroText.Text = "KONOZIS HUB"
IntroText.TextColor3 = Color3.fromRGB(180, 80, 255)
IntroText.TextSize = 36
IntroText.Font = Enum.Font.GothamBold
IntroText.ZIndex = 1000

-- 2. ГЛАВНОЕ ОКНО МЕНЮ
local Main = Instance.new("Frame", Gui)
Main.BackgroundColor3 = Color3.fromRGB(18, 10, 26)
Main.Position = UDim2.new(0.5, -120, 0.5, -122)
Main.Size = UDim2.new(0, 240, 0, 245)
Main.Visible = false -- Скрыто на время интро
Main.Active = true
Main.Draggable = true
Instance.new("UICorner", Main).CornerRadius = UDim.new(0, 12)

local MainStroke = Instance.new("UIStroke", Main)
MainStroke.Color = Color3.fromRGB(90, 35, 140)
MainStroke.Thickness = 1.5

-- Шапка
local Title = Instance.new("TextLabel", Main)
Title.BackgroundColor3 = Color3.fromRGB(28, 14, 42)
Title.Size = UDim2.new(1, 0, 0, 36)
Title.Text = "   konozis hub"
Title.TextColor3 = Color3.fromRGB(230, 190, 255)
Title.TextSize = 13
Title.Font = Enum.Font.GothamSemibold
Title.TextXAlignment = Enum.TextXAlignment.Left
Instance.new("UICorner", Title).CornerRadius = UDim.new(0, 12)

local TitleCover = Instance.new("Frame", Title)
TitleCover.BackgroundColor3 = Color3.fromRGB(28, 14, 42)
TitleCover.BorderSizePixel = 0
TitleCover.Position = UDim2.new(0, 0, 0.5, 0)
TitleCover.Size = UDim2.new(1, 0, 0.5, 0)

-- Крестик (сворачивает меню в круг)
local Close = Instance.new("TextButton", Title)
Close.BackgroundTransparency = 1
Close.Position = UDim2.new(1, -36, 0, 0)
Close.Size = UDim2.new(0, 36, 1, 0)
Close.Text = "✕"
Close.TextColor3 = Color3.fromRGB(255, 110, 110)
Close.TextSize = 13
Close.Font = Enum.Font.GothamBold

-- 3. КРУГЛАЯ КНОПКА ВОЗВРАТА ПО ЦЕНТРУ
local CenterCircle = Instance.new("TextButton", Gui)
CenterCircle.BackgroundColor3 = Color3.fromRGB(35, 15, 60)
CenterCircle.Position = UDim2.new(0.5, -25, 0.5, -25)
CenterCircle.Size = UDim2.new(0, 50, 0, 50)
CenterCircle.Text = "K"
CenterCircle.TextColor3 = Color3.fromRGB(230, 180, 255)
CenterCircle.TextSize = 20
CenterCircle.Font = Enum.Font.GothamBold
CenterCircle.Visible = false
CenterCircle.Active = true
CenterCircle.Draggable = true
Instance.new("UICorner", CenterCircle).CornerRadius = UDim.new(1, 0)

local CircleStroke = Instance.new("UIStroke", CenterCircle)
CircleStroke.Color = Color3.fromRGB(160, 80, 240)
CircleStroke.Thickness = 2

-- Вкладки (World / Bike)
local Tab1Btn = Instance.new("TextButton", Main)
Tab1Btn.BackgroundColor3 = Color3.fromRGB(65, 25, 100)
Tab1Btn.Position = UDim2.new(0.06, 0, 0, 46)
Tab1Btn.Size = UDim2.new(0, 102, 0, 28)
Tab1Btn.Text = "World"
Tab1Btn.TextColor3 = Color3.fromRGB(255, 255, 255)
Tab1Btn.TextSize = 12
Tab1Btn.Font = Enum.Font.GothamMedium
Instance.new("UICorner", Tab1Btn).CornerRadius = UDim.new(0, 8)

local Tab2Btn = Instance.new("TextButton", Main)
Tab2Btn.BackgroundColor3 = Color3.fromRGB(30, 15, 48)
Tab2Btn.Position = UDim2.new(0.52, 0, 0, 46)
Tab2Btn.Size = UDim2.new(0, 102, 0, 28)
Tab2Btn.Text = "Bike"
Tab2Btn.TextColor3 = Color3.fromRGB(170, 140, 200)
Tab2Btn.TextSize = 12
Tab2Btn.Font = Enum.Font.GothamMedium
Instance.new("UICorner", Tab2Btn).CornerRadius = UDim.new(0, 8)

local Tab1 = Instance.new("Frame", Main)
Tab1.BackgroundTransparency = 1
Tab1.Position = UDim2.new(0, 0, 0, 84)
Tab1.Size = UDim2.new(1, 0, 1, -84)

local Tab2 = Instance.new("Frame", Main)
Tab2.BackgroundTransparency = 1
Tab2.Position = UDim2.new(0, 0, 0, 84)
Tab2.Size = UDim2.new(1, 0, 1, -84)
Tab2.Visible = false

-- Вкладка World: Night Mode
local NightBtn = Instance.new("TextButton", Tab1)
NightBtn.BackgroundColor3 = Color3.fromRGB(35, 18, 55)
NightBtn.Position = UDim2.new(0.06, 0, 0.08, 0)
NightBtn.Size = UDim2.new(0, 210, 0, 44)
NightBtn.Text = "Night Mode: OFF"
NightBtn.TextColor3 = Color3.fromRGB(240, 240, 240)
NightBtn.TextSize = 12
NightBtn.Font = Enum.Font.GothamMedium
Instance.new("UICorner", NightBtn).CornerRadius = UDim.new(0, 8)

local NightStroke = Instance.new("UIStroke", NightBtn)
NightStroke.Color = Color3.fromRGB(75, 40, 110)
NightStroke.Transparency = 0.5

-- Вкладка Bike: RGB
local RGBBtn = Instance.new("TextButton", Tab2)
RGBBtn.BackgroundColor3 = Color3.fromRGB(35, 18, 55)
RGBBtn.Position = UDim2.new(0.06, 0, 0.05, 0)
RGBBtn.Size = UDim2.new(0, 210, 0, 36)
RGBBtn.Text = "RGB Motorcycle: OFF"
RGBBtn.TextColor3 = Color3.fromRGB(240, 240, 240)
RGBBtn.TextSize = 11
RGBBtn.Font = Enum.Font.GothamMedium
Instance.new("UICorner", RGBBtn).CornerRadius = UDim.new(0, 8)

local RGBStroke = Instance.new("UIStroke", RGBBtn)
RGBStroke.Color = Color3.fromRGB(75, 40, 110)
RGBStroke.Transparency = 0.5

local LightsLabel = Instance.new("TextLabel", Tab2)
LightsLabel.BackgroundTransparency = 1
LightsLabel.Position = UDim2.new(0.06, 0, 0.42, 0)
LightsLabel.Size = UDim2.new(0, 210, 0, 20)
LightsLabel.Text = "Headlights Palette (8 Colors)"
LightsLabel.TextColor3 = Color3.fromRGB(180, 150, 210)
LightsLabel.TextSize = 10
LightsLabel.Font = Enum.Font.GothamBold
LightsLabel.TextXAlignment = Enum.TextXAlignment.Left

-- 8 цветов фар
local headColors = {
	Color3.fromRGB(255, 255, 255),
	Color3.fromRGB(255, 50, 50),
	Color3.fromRGB(50, 255, 50),
	Color3.fromRGB(50, 150, 255),
	Color3.fromRGB(255, 255, 0),
	Color3.fromRGB(255, 100, 255),
	Color3.fromRGB(0, 255, 255),
	Color3.fromRGB(255, 128, 0)
}
local selectedHeadColor = headColors[1]

local PaletteFrame = Instance.new("Frame", Tab2)
PaletteFrame.BackgroundTransparency = 1
PaletteFrame.Position = UDim2.new(0.06, 0, 0.53, 0)
PaletteFrame.Size = UDim2.new(0, 210, 0, 68)

for i, col in ipairs(headColors) do
	local row = math.floor((i - 1) / 4)
	local colIndex = (i - 1) % 4

	local colorBtn = Instance.new("TextButton", PaletteFrame)
	colorBtn.BackgroundColor3 = col
	colorBtn.Position = UDim2.new(0, colIndex * 54, 0, row * 34)
	colorBtn.Size = UDim2.new(0, 48, 0, 28)
	colorBtn.Text = ""
	Instance.new("UICorner", colorBtn).CornerRadius = UDim.new(0, 6)

	local btnStroke = Instance.new("UIStroke", colorBtn)
	btnStroke.Color = Color3.fromRGB(255, 255, 255)
	btnStroke.Transparency = 0.6
	btnStroke.Thickness = 1

	colorBtn.MouseButton1Click:Connect(function()
		selectedHeadColor = col
	end)
end

-- Переключение табов
Tab1Btn.MouseButton1Click:Connect(function()
	Tab1.Visible, Tab2.Visible = true, false
	Tab1Btn.BackgroundColor3 = Color3.fromRGB(65, 25, 100)
	Tab1Btn.TextColor3 = Color3.fromRGB(255, 255, 255)
	Tab2Btn.BackgroundColor3 = Color3.fromRGB(30, 15, 48)
	Tab2Btn.TextColor3 = Color3.fromRGB(170, 140, 200)
end)

Tab2Btn.MouseButton1Click:Connect(function()
	Tab1.Visible, Tab2.Visible = false, true
	Tab2Btn.BackgroundColor3 = Color3.fromRGB(65, 25, 100)
	Tab2Btn.TextColor3 = Color3.fromRGB(255, 255, 255)
	Tab1Btn.BackgroundColor3 = Color3.fromRGB(30, 15, 48)
	Tab1Btn.TextColor3 = Color3.fromRGB(170, 140, 200)
end)

Close.MouseButton1Click:Connect(function()
	Main.Visible = false
	CenterCircle.Visible = true
end)

CenterCircle.MouseButton1Click:Connect(function()
	CenterCircle.Visible = false
	Main.Visible = true
end)

-- Ночной режим
local nightOn = false
NightBtn.MouseButton1Click:Connect(function()
	nightOn = not nightOn
	if nightOn then
		NightBtn.Text = "Night Mode: ON"
		NightBtn.BackgroundColor3 = Color3.fromRGB(85, 35, 130)
		NightStroke.Color = Color3.fromRGB(160, 80, 230)
		Lighting.ClockTime = 0
		Lighting.Brightness = 0.5
	else
		NightBtn.Text = "Night Mode: OFF"
		NightBtn.BackgroundColor3 = Color3.fromRGB(35, 18, 55)
		NightStroke.Color = Color3.fromRGB(75, 40, 110)
		Lighting.ClockTime = 14
		Lighting.Brightness = 2
	end
end)

-- RGB переключатель
local rgbOn = false
RGBBtn.MouseButton1Click:Connect(function()
	rgbOn = not rgbOn
	if rgbOn then
		RGBBtn.Text = "RGB Motorcycle: ON"
		RGBBtn.BackgroundColor3 = Color3.fromRGB(85, 35, 130)
		RGBStroke.Color = Color3.fromRGB(160, 80, 230)
	else
		RGBBtn.Text = "RGB Motorcycle: OFF"
		RGBBtn.BackgroundColor3 = Color3.fromRGB(35, 18, 55)
		RGBStroke.Color = Color3.fromRGB(75, 40, 110)
	end
end)

-- 4. ТОЧНЫЙ ТАЙМЕР ИНТРО (ровно 5 секунд)
task.spawn(function()
	task.wait(5)
	IntroBg:Destroy()
	Main.Visible = true
	print("Konozis Hub успешно запущен!")
end)

-- 5. ФОНОВАЯ ЛОГИКА (Подсветка байка + конусные фары SpotLight)
local hl = nil
local customSpotLight = nil

local function getBike()
	local char = player.Character
	if not char then return nil end
	local hum = char:FindFirstChildOfClass("Humanoid")
	if hum and hum.SeatPart then
		local m = hum.SeatPart.Parent
		while m and m ~= workspace and m ~= char do
			if m:IsA("Model") then return m end
			m = m.Parent
		end
	end
	return nil
end

RunService.RenderStepped:Connect(function()
	if rgbOn then
		local bike = getBike()
		if bike then
			if not hl or hl.Parent ~= bike then
				if hl then hl:Destroy() end
				hl = Instance.new("Highlight", bike)
				hl.Adornee = bike
				hl.OutlineColor = Color3.new(0, 0, 0)
				hl.FillTransparency = 0.2
				hl.DepthMode = Enum.HighlightDepthMode.Occluded
			end
			hl.FillColor = Color3.fromHSV((tick() % 4) / 4, 1, 1)

			if not customSpotLight or customSpotLight.Parent ~= bike then
				if customSpotLight then customSpotLight:Destroy() end
				local targetPart = bike.PrimaryPart or bike:FindFirstChildWhichIsA("BasePart")
				if targetPart then
					customSpotLight = Instance.new("SpotLight", targetPart)
					customSpotLight.Angle = 60
					customSpotLight.Range = 40
					customSpotLight.Brightness = 10
					customSpotLight.Face = Enum.NormalId.Front
				end
			end

			if customSpotLight then
				customSpotLight.Color = selectedHeadColor
				customSpotLight.Enabled = true
			end
		else
			if hl then hl:Destroy(); hl = nil end
			if customSpotLight then customSpotLight:Destroy(); customSpotLight = nil end
		end
	else
		if hl then hl:Destroy(); hl = nil end
		if customSpotLight then customSpotLight:Destroy(); customSpotLight = nil end
	end
end)
