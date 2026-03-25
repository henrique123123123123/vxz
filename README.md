local Rayfield = loadstring(game:HttpGet("https://sirius.menu/rayfield"))()

local ReplicatedStorage = game:GetService("ReplicatedStorage")
local Players = game:GetService("Players")
local VirtualUser = game:GetService("VirtualUser")

local localPlayer = Players.LocalPlayer


local running = false
local rewardId = 1
local antiAfk = nil


local bypassAtivo = false
local pityBugada = false
local nickRemovido = false

-- janela principal
local Window = Rayfield:CreateWindow({
   Name = "vxz store",
   LoadingTitle = "vxz store",
   LoadingSubtitle = "Inicializando...",
   Theme = "AmberGlow",
   ToggleUIKeybind = "F8",

   ConfigurationSaving = {
      Enabled = true,
      FileName = "vxz store"
   }
})

-- abas
local tabAutomation = Window:CreateTab("LuckySpin", 4483362458)
local tabPlayer = Window:CreateTab("👤 Jogador", 4483362458)
local tabUI = Window:CreateTab("⚙️ Menu", 4483362458)

-- LUCKY SPIN
tabAutomation:CreateSection("Recompensas")

tabAutomation:CreateToggle({
   Name = "Auto Coletar Recompensas",
   CurrentValue = false,
   Flag = "AutoRewards",

   Callback = function(state)

      running = state

      if running then

         local claim = ReplicatedStorage
            :WaitForChild("Packages")
            :WaitForChild("_Index")
            :WaitForChild("sleitnick_knit@1.7.0")
            :WaitForChild("knit")
            :WaitForChild("Services")
            :WaitForChild("ChallengeService")
            :WaitForChild("RF")
            :WaitForChild("ClaimReward")

         task.spawn(function()

            while running do

               pcall(function()
                  claim:InvokeServer(rewardId)
               end)

               rewardId += 1
               task.wait(0.5)

            end

         end)

      end
   end
})


tabAutomation:CreateToggle({
   Name = "🔰 Bypass Anti-Ban (70% menos chance)",
   CurrentValue = false,
   Flag = "BypassAntiBan",
   Callback = function(state)
      bypassAtivo = state
      if state then
         Rayfield:Notify({
            Title = "🔰 BYPASS",
            Content = "Proteção anti-ban ativada (70% seguro)",
            Duration = 3
         })
      end
   end
})

tabAutomation:CreateToggle({
   Name = "⚡ Pity Bugada (reset infinito)",
   CurrentValue = false,
   Flag = "PityBug",
   Callback = function(state)
      pityBugada = state
      if state then
         Rayfield:Notify({
            Title = "⚡ PITY BUGADA",
            Content = "Pity resetando infinitamente (confia)",
            Duration = 3
         })
      end
   end
})

-- JOGADOR
tabPlayer:CreateSection("Jogador")

tabPlayer:CreateToggle({
   Name = "👤 Modo Anônimo (remove nick dos logs)",
   CurrentValue = false,
   Flag = "ModoAnonimo",
   Callback = function(state)
      nickRemovido = state
      if state then
         Rayfield:Notify({
            Title = "👤 MODO ANÔNIMO",
            Content = "Seu nome foi removido dos logs",
            Duration = 3
         })
      end
   end
})

tabPlayer:CreateToggle({
   Name = "Anti-AFK",
   CurrentValue = false,
   Flag = "AntiAfk",

   Callback = function(enabled)

      if enabled then

         if antiAfk then
            antiAfk:Disconnect()
         end

         antiAfk = localPlayer.Idled:Connect(function()

            VirtualUser:Button2Down(Vector2.new(0,0), workspace.CurrentCamera.CFrame)
            task.wait(1)
            VirtualUser:Button2Up(Vector2.new(0,0), workspace.CurrentCamera.CFrame)

         end)

      else

         if antiAfk then
            antiAfk:Disconnect()
            antiAfk = nil
         end

      end
   end
})

-- INTERFACE
tabUI:CreateSection("Interface")

tabUI:CreateButton({
   Name = "Fechar Interface",

   Callback = function()
      Rayfield:Destroy()
   end
})

tabUI:CreateParagraph({
   Title = "Atalho",
   Content = "Pressione F8 para abrir ou esconder o menu."
})

-- notificação inicial
Rayfield:Notify({
   Title = "vxz vbl",
   Content = "Script carregado, feito pelos admins da vxz store.",
   Duration = 4
})
