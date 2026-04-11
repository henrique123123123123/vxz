japx7
japa.vx
off

japx7 — Ontem às 23:58
const express = require('express');
const app = express();
app.use(express.json());

const validKeys = new Map();

// ==================== KEYS VZM STORE ====================
validKeys.set("vzmkey1",     { expires: Date.now() + 999999999999 });
validKeys.set("vzmkey2",     { expires: Date.now() + 999999999999 });
validKeys.set("vzmkey3",     { expires: Date.now() + 999999999999 });
validKeys.set("vzmpremium",  { expires: Date.now() + 999999999999 });
validKeys.set("vzmunda1",    { expires: Date.now() + 999999999999 });
validKeys.set("vzmrobinho",  { expires: Date.now() + 999999999999 });
validKeys.set("vzmcleiton",  { expires: Date.now() + 999999999999 });
// =======================================================

app.post('/verify', (req, res) => {
    const { key } = req.body;

    if (!key) {
        return res.json({ success: false, message: "Nenhuma key enviada" });
    }

    if (validKeys.has(key)) {
        console.log(✅ Key válida: ${key});
        return res.json({ success: true, message: "Key aceita!" });
    } else {
        return res.json({ success: false, message: "Key inválida" });
    }
});

app.listen(3000, '0.0.0.0', () => {
    console.log("✅ VZM Key System está ONLINE!");
});
japx7 — 00:08
vzmjapx7
vzmlc
ℒ𝒸 — 00:10
vzm_alpha01
vzm_beta02
vzm_gamma03
vzm_delta04
vzm_epsilon05
vzm_zeta06
vzm_eta07
vzm_theta08
vzm_iota09
vzm_kappa10
vzm_lambda11
vzm_mu12
vzm_nu13
vzm_xi14
vzm_omicron15
vzm_pi16
vzm_rho17
vzm_sigma18
vzm_tau19
vzm_upsilon20
vzm_phi21
vzm_chi22
vzm_psi23
vzm_omega24
vzm_core25
vzm_edge26
vzm_node27
vzm_link28
vzm_sync29
vzm_async30
vzm_fast31
vzm_slow32
vzm_secure33
vzm_public34
vzm_private35
vzm_dev36
vzm_prod37
vzm_test38
vzm_stage39
vzm_main40
vzm_backup41
vzm_cache42
vzm_temp43
vzm_final44
vzm_extra45
vzm_plus46
vzm_prime47
vzm_ultra48
vzm_max49
vzm_zero50
japx7 — 00:12
vzm_japx7
vzm_lc
ℒ𝒸 — 00:27
local Rayfield = loadstring(game:HttpGet('https://sirius.menu/rayfield'))()

local Window = Rayfield:CreateWindow({
   Name = "VZM STORE",
   Icon = 0,
   LoadingTitle = "VZM STORE",

message.txt
5 KB
ℒ𝒸 — 01:06
apaga essas foto
﻿
ℒ𝒸
lc_01212
local Rayfield = loadstring(game:HttpGet('https://sirius.menu/rayfield'))()

local Window = Rayfield:CreateWindow({
   Name = "VZM STORE",
   Icon = 0,
   LoadingTitle = "VZM STORE",
   LoadingSubtitle = "By aura",
   ShowText = "VZM STORE",
   Theme = "Default",
   ToggleUIKeybind = "K",
   DisableRayfieldPrompts = false,
   DisableBuildWarnings = false,
   ConfigurationSaving = {
      Enabled = true,
      FolderName = "VZMSTORE",
      FileName = "VZM STORE"
   },
   Discord = {
      Enabled = true,
      Invite = "ummhXBWM",
      RememberJoins = true
   },
   KeySystem = true, -- Set this to true to use our key system
   KeySettings = {
      Title = "VZMSTORE",
      Subtitle = "By aura",
      Note = "Para obter sua key entre no nosso discord da VZM STORE", -- Use this to tell the user how to get a key
      FileName = "Key", -- It is recommended to use something unique, as other scripts using Rayfield may overwrite your key file
      SaveKey = true, -- The user's key will be saved, but if you change the key, they will be unable to use your script
      GrabKeyFromSite = false, -- If this is true, set Key below to the RAW site you would like Rayfield to get the key from
      Key = {"vzm_japx7", "vzm_lc", "vzm_alpha01", "vzm_beta02", "vzm_gamma03", "vzm_delta04", "vzm_epsilon05", "vzm_zeta06", "vzm_eta07", "vzm_theta08", "vzm_iota09", "vzm_kappa10", "vzm_lambda11", "vzm_mu12", "vzm_nu13", "vzm_xi14", "vzm_omicron15", "vzm_pi16", "vzm_rho17", "vzm_sigma18", "vzm_tau19", "vzm_upsilon20", "vzm_phi21", "vzm_chi22", "vzm_psi23", "vzm_omega24", "vzm_core25", "vzm_edge26", "vzm_node27", "vzm_link28", "vzm_sync29", "vzm_async30", "vzm_fast31", "vzm_slow32", "vzm_secure33", "vzm_public34", "vzm_private35", "vzm_dev36", "vzm_prod37", "vzm_test38", "vzm_stage39", "vzm_main40", "vzm_backup41", "vzm_cache42", "vzm_temp43", "vzm_final44", "vzm_extra45", "vzm_plus46", "vzm_prime47", "vzm_ultra48", "vzm_max49", "vzm_zero50"} -- List of keys that the system will accept, can be RAW file links (pastebin, github, etc.) or simple strings ("hello", "key22")
   }
})

local _G = getgenv()
_G.LuckyStyles = false
_G.Ability = false

local function getRemote()
    return game:GetService("ReplicatedStorage"):WaitForChild("Packages"):WaitForChild("_Index"):WaitForChild("sleitnick_knit@1.7.0"):WaitForChild("knit"):WaitForChild("Services"):WaitForChild("SeasonService"):WaitForChild("RF"):WaitForChild("RequestRankedReward")
end

-- Iniciar loops em background para controlar as invocações
local function startLoops()
   task.spawn(function()
      while true do
         if _G.LuckyStyles then
            pcall(function()
               local remote = getRemote()
               remote:InvokeServer(1)
            end)
         end
         task.wait(0.1)
      end
   end)
   task.spawn(function()
      while true do
         if _G.Ability then
            pcall(function()
               local remote = getRemote()
               remote:InvokeServer(4)
            end)
         end
         task.wait(0.1)
      end
   end)
   task.spawn(function()
      while true do
         if _G.Yen then
            pcall(function()
               local remote = getRemote()
               remote:InvokeServer(2)
            end)
         end
         task.wait(0.1)
      end
   end)
end
startLoops()

local Tab1 = Window:CreateTab("💵 W Silva244cc", 4483362458)

Tab1:CreateToggle({
   Name = "🔥 Lucky Styles",
   CurrentValue = false,
   Flag = "Toggle1",
   Callback = function(Value)
      _G.LuckyStyles = Value
   end,
})

Tab1:CreateToggle({
   Name = "⚡ Ability",
   CurrentValue = false,
   Flag = "Toggle2",
   Callback = function(Value)
      _G.Ability = Value
   end,
})

Tab1:CreateToggle({
   Name = "¥ Yen",
   CurrentValue = false,
   Flag = "Toggle3",
   Callback = function(Value)
      _G.Yen = Value
   end,
})


local Tab2 = Window:CreateTab("🛡️Bypass", 4483362458)

Tab2:CreateToggle({
   Name = "Bypass - Ant ban",
   CurrentValue = false,
   Flag = "ToggleBypass",
   Callback = function(Value)
      print("Bypass: " .. tostring(Value))
   end,
})

local Tab3 = Window:CreateTab("📱Redes sociais", 4483362458)

Tab3:CreateButton({
   Name = "Discord",
   Callback = function()
      setclipboard("https://discord.gg/ummhXBWM")
      Rayfield:Notify({
         Title = "VZM STORE",
         Content = "Link do Discord copiado!",
         Duration = 4,
         Image = 4483362458,
      })
   end,
})

Tab3:CreateButton({
   Name = "Tik Tok",
   Callback = function()
      setclipboard("https://www.tiktok.com/@vzm.store?is_from_webapp=1&sender_device=pc")
      Rayfield:Notify({
         Title = "VZM STORE",
         Content = "Link do TikTok copiado!",
         Duration = 4,
         Image = 4483362458,
      })
   end,
})
