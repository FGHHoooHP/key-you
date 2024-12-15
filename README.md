
local requiredKeys = {
    [7144504097] = "Water-hub-656a-423f-9618-fe1672243f7e", -- ผู้เล่น ID 7144504097 ต้องกรอกคีย์นี้
    [5370483427] = "Water-hub-656e-465f-9328-fe1542243f7e"
    [2225408985] = "Water-hub-d748-4ab6-881d-6dd6989fcec4"
    
}

-- ฟังก์ชันเช็คผู้เล่นและคีย์
local playerID = game.Players.LocalPlayer.UserId -- ใช้ ID ของผู้เล่นปัจจุบัน
local player = game.Players:GetPlayerByUserId(playerID)

-- ถ้าผู้เล่นมีในรายชื่อ
if player then
    local requiredKey = requiredKeys[playerID] -- คีย์ที่ต้องกรอกตาม ID ของผู้เล่น
    if requiredKey then
        local enteredKey = getgenv().key -- คีย์ที่ผู้เล่นกรอกมา

        -- ตรวจสอบคีย์ที่ผู้เล่นกรอก
        if enteredKey == requiredKey then
            -- คีย์ถูกต้อง
            loadstring(game:HttpGet("https://raw.githubusercontent.com/FGHHoooHP/FarmBone/main/README.md"))()
            -- ดำเนินการเพิ่มเติม (แสดง UI, เปิดฟีเจอร์ ฯลฯ)
        else
            -- คีย์ไม่ถูกต้อง
            player:Kick("Invalid key!") -- เตะผู้เล่นออกจากเกม
        end
    else
        -- ถ้าผู้เล่นไม่มีคีย์ที่กำหนดไว้
        print("No key requirement for this player.")
    end
else
    -- ถ้าผู้เล่นไม่พบในเกม
    print("Player not found.")
end
