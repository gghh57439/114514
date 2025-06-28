-- 创建黑色 UI
local ScreenGui = Instance.new("ScreenGui")
ScreenGui.Name = "TrollGui"
ScreenGui.Parent = game:GetService("CoreGui") -- 注入器通常允许修改 CoreGui

local Frame = Instance.new("Frame")
Frame.Size = UDim2.new(0.3, 0, 0.2, 0) -- 宽度 30%，高度 20%
Frame.Position = UDim2.new(0.35, 0, 0.4, 0) -- 居中
Frame.BackgroundColor3 = Color3.new(0, 0, 0)
Frame.BorderSizePixel = 2
Frame.BorderColor3 = Color3.new(0, 1, 0) -- 绿色边框
Frame.Parent = ScreenGui

local TextLabel = Instance.new("TextLabel")
TextLabel.Size = UDim2.new(0.9, 0, 0.6, 0)
TextLabel.Position = UDim2.new(0.05, 0, 0.1, 0)
TextLabel.BackgroundTransparency = 1
TextLabel.Text = ""
TextLabel.TextColor3 = Color3.new(1, 1, 1) -- 白色文字
TextLabel.Font = Enum.Font.SourceSansBold
TextLabel.TextSize = 18
TextLabel.Parent = Frame

local ExecuteButton = Instance.new("TextButton")
ExecuteButton.Size = UDim2.new(0.6, 0, 0.2, 0)
ExecuteButton.Position = UDim2.new(0.2, 0, 0.7, 0)
ExecuteButton.BackgroundColor3 = Color3.new(0, 1, 0) -- 绿色按钮
ExecuteButton.Text = "执行"
ExecuteButton.TextColor3 = Color3.new(0, 0, 0)
ExecuteButton.Font = Enum.Font.SourceSansBold
ExecuteButton.TextSize = 16
ExecuteButton.Parent = Frame

-- 点击按钮后执行
ExecuteButton.MouseButton1Click:Connect(function()
    ExecuteButton.Visible = false -- 隐藏按钮

    -- 逐步显示消息
    TextLabel.Text = "欢迎使用本脚本"
    task.wait(2)
    TextLabel.Text = "正在检测服务器"
    task.wait(2)
    TextLabel.Text = "检测成功，正在执行获取R币"
    task.wait(2)
    TextLabel.Text = "稍等..."
    task.wait(2)
    TextLabel.Text = "获取失败，正在被服务器反追踪"

    -- 3秒后踢出玩家
    task.wait(3)
    game:GetService("Players").LocalPlayer:Kick("⚠️ 检测到作弊行为，你已被踢出！")
end)