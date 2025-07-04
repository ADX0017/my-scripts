-- ตั้งคีย์ที่ต้องการให้ตรงกับผู้ใช้
local correctKey = "ANOS WIN"

-- UI พื้นฐานของระบบ Key
local ScreenGui = Instance.new("ScreenGui", game.CoreGui)
local Frame = Instance.new("Frame", ScreenGui)
Frame.Size = UDim2.new(0, 300, 0, 150)
Frame.Position = UDim2.new(0.5, -150, 0.5, -75)
Frame.BackgroundColor3 = Color3.fromRGB(35, 35, 35)
Frame.BorderSizePixel = 0
Frame.Name = "KeySystem"

local TextBox = Instance.new("TextBox", Frame)
TextBox.PlaceholderText = "Enter your key..."
TextBox.Size = UDim2.new(0, 260, 0, 40)
TextBox.Position = UDim2.new(0, 20, 0, 20)
TextBox.Text = ""
TextBox.TextScaled = true
TextBox.BackgroundColor3 = Color3.fromRGB(55, 55, 55)
TextBox.TextColor3 = Color3.fromRGB(255,255,255)

local Submit = Instance.new("TextButton", Frame)
Submit.Text = "SUBMIT"
Submit.Size = UDim2.new(0, 260, 0, 40)
Submit.Position = UDim2.new(0, 20, 0, 80)
Submit.BackgroundColor3 = Color3.fromRGB(70, 150, 70)
Submit.TextColor3 = Color3.fromRGB(255,255,255)
Submit.TextScaled = true

Submit.MouseButton1Click:Connect(function()
	if TextBox.Text == correctKey then
		Frame:Destroy() -- ปิด UI
		-- โหลดสคริปต์หลังผ่าน Key
		loadstring(game:HttpGet("https://pastefy.app/ejCa4ird/raw"))()
	else
		Submit.Text = "❌ WRONG KEY"
		wait(1.2)
		Submit.Text = "SUBMIT"
	end
end)
