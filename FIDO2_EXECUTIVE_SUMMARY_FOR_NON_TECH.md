---
marp: true
theme: gaia
_class: lead
paginate: true
backgroundColor: #ffffff
color: #0f172a
header: '🏢 FIDO2 / WebAuthn 企業級無密碼身分安全中心'
footer: 'FIDO2 系統核心資安團隊 ｜ 決策者與非技術人員導覽手冊'
size: 16:9
style: |
  section {
    font-family: "PingFang TC", "Microsoft JhengHei", "Noto Sans CJK TC", sans-serif;
    font-size: 21px;
    padding: 38px 50px;
    justify-content: flex-start;
    line-height: 1.6;
    background-color: #ffffff;
    color: #0f172a;
  }
  h1 { color: #0f2942 !important; font-size: 30px; border-bottom: 3px solid #1d4ed8; padding-bottom: 6px; margin-top: 0; margin-bottom: 14px; font-weight: 800; }
  h2 { color: #1e3a8a !important; font-size: 24px; border-bottom: 2px solid #3b82f6; padding-bottom: 5px; margin-top: 0; margin-bottom: 12px; font-weight: 800; }
  h3 { color: #1e40af !important; font-size: 20px; margin-top: 8px; margin-bottom: 8px; font-weight: 700; }
  p, li { line-height: 1.6; font-size: 18.5px; margin-bottom: 8px; color: #0f172a !important; font-weight: 500; }
  strong { color: #020617 !important; font-weight: 800; }
  ul, ol { margin-top: 4px; margin-bottom: 10px; padding-left: 24px; }
  table { font-size: 16.5px; width: 100%; border-collapse: collapse; margin-top: 8px; margin-bottom: 10px; }
  th, td { border: 2px solid #64748b; padding: 8px 12px; color: #0f172a !important; font-weight: 500; }
  th { background-color: #e2e8f0; color: #091e3a !important; font-weight: 800; }
  .callout-box { background-color: #eff6ff; border-left: 6px solid #1d4ed8; padding: 12px 18px; border-radius: 6px; margin: 10px 0; font-size: 18px; color: #0f172a; border-top: 1.5px solid #bfdbfe; border-right: 1.5px solid #bfdbfe; border-bottom: 1.5px solid #bfdbfe; }
  .warning-box { background-color: #fffbeb; border-left: 6px solid #d97706; padding: 12px 18px; border-radius: 6px; margin: 10px 0; font-size: 18px; color: #451a03; border-top: 1.5px solid #fde68a; border-right: 1.5px solid #fde68a; border-bottom: 1.5px solid #fde68a; }
  .success-box { background-color: #f0fdf4; border-left: 6px solid #16a34a; padding: 12px 18px; border-radius: 6px; margin: 10px 0; font-size: 18px; color: #052e16; border-top: 1.5px solid #bbf7d0; border-right: 1.5px solid #bbf7d0; border-bottom: 1.5px solid #bbf7d0; }
  pre, code {
    background-color: #0f172a !important;
    color: #38bdf8 !important;
    font-weight: 700 !important;
    border: 2px solid #0284c7 !important;
    font-family: 'Cascadia Code', Consolas, 'Courier New', monospace;
  }
  pre { font-size: 14.5px; line-height: 1.4; padding: 14px 18px; border-radius: 8px; box-shadow: 0 4px 6px -1px rgba(0,0,0,0.25); }
  footer, header { font-size: 13px; opacity: 0.95; color: #1e293b !important; font-weight: 700; }
  .badge { display: inline-block; padding: 3px 9px; border-radius: 4px; font-size: 13.5px; font-weight: 800; margin-right: 6px; }
  .badge-primary { background: #dbeafe; color: #1e40af; border: 1.5px solid #3b82f6; }
  .badge-success { background: #dcfce7; color: #166534; border: 1.5px solid #22c55e; }
---

<!-- _class: lead -->
<div style="background: linear-gradient(135deg, #0a1f38 0%, #163e68 100%); color: #ffffff; padding: 42px 30px; border-radius: 12px; text-align: center; box-shadow: 0 10px 20px -3px rgba(0,0,0,0.3);">
  <h1 style="color: #ffffff !important; font-size: 36px; font-weight: 800; margin-bottom: 14px; border: none; text-shadow: 0 2px 4px rgba(0,0,0,0.5);">🏢 FIDO2 / WebAuthn 企業級無密碼身分安全中心</h1>
  <h2 style="color: #60a5fa !important; font-size: 24px; font-weight: 700; margin-bottom: 24px; border: none; text-shadow: 0 1px 3px rgba(0,0,0,0.5);">決策者與非技術人員導覽手冊 (Executive Summary & Presentation)</h2>
  <p style="color: #f1f5f9 !important; font-size: 18px; margin: 6px 0; font-weight: 600;"><strong>報告單位：</strong> FIDO2 系統核心資安團隊</p>
  <p style="color: #f1f5f9 !important; font-size: 18px; margin: 6px 0; font-weight: 600;"><strong>系統版本：</strong> v1.0.0 (Spring Boot 3.4 & W3C WebAuthn Level 3 Conformance 100%)</p>
  <p style="color: #cbd5e1 !important; font-size: 16px; margin: 6px 0;"><strong>報告日期：</strong> 2026 年 11 月</p>
</div>

---

## 📑 簡報目錄 (Agenda)

1. **三分鐘看懂**：為什麼全世界都在淘汰傳統密碼？
2. **生活化比喻**：什麼是 FIDO2 與 Passkey？（瑞士銀行保險箱）
3. **系統核心功能**：五大核心功能與商業價值總覽
4. **防釣魚物理探測**：為什麼手機掃碼一定要開啟藍牙？
5. **企業管理與審計**：特殊最高管理員 (ADMIN) 專屬後台與時間軸
6. **極端災難應變**：換手機、設備遺失壞掉怎麼辦？（離線緊急復原碼）
7. **常見疑問解答**：決策主管最關心的 FAQ（生物特徵、資料庫脫褲）
8. **法規遵循效益**：國際標準認證 100% 與企業競爭力

---

## 1. 為什麼全世界都在淘汰傳統密碼？

在過去 30 年中，幾乎所有系統都依賴「帳號 + 密碼 + 簡訊 OTP 驗證碼」來保護帳號。現代資安威脅已經證實：**密碼是企業最脆弱的安全漏洞！**

### 傳統密碼的四大致命痛點：
1. **密碼記不住，重複使用或貼在便條紙**：
   員工平均需記憶超過 30 組密碼，導致習慣用「生日、電話、Company123!」，一人被駭，全公司淪陷。
2. **中間人假網站釣魚 (Phishing)**：
   駭客製作外觀一模一樣的假登入頁面，員工輸入帳密與簡訊 6 位數驗證碼後，駭客在 5 秒內同時截獲並登入系統（簡訊與 TOTP 驗證碼完全無法防範即時代理釣魚）。

---

## 1. 密碼痛點分析與 FIDO2 核心變革

### 傳統密碼痛點續篇：
3. **伺服器資料庫被盜竊（脫褲）**：
   若伺服器資料庫遭駭客入侵，資料庫儲存的密碼雜湊一旦被暴力破解，所有客戶與員工帳號全數外洩。
4. **客服成本居高不下**：
   統計顯示，跨國企業內部 IT Helpdesk 客服電話中，高達 **35% ~ 45%** 的工作量都花在處理「使用者忘記密碼、帳號被鎖定、重設密碼」。

<div class="success-box">
<strong>💡 FIDO2 的核心變革：</strong><br>
徹底將「密碼」從地球上抹除！不再有任何密碼需要記憶，不再有密碼會在網路上傳輸，伺服器資料庫也根本不儲存您的密碼！
</div>

---

## 2. 什麼是 FIDO2 與 Passkey？——瑞士銀行比喻

如果沒有密碼，系統要怎麼知道「我是我」？

### 🏦 經典比喻：瑞士銀行的專屬保險箱
想像您在瑞士銀行租用了一個最高等級的專屬保險庫：

| 角色與元件 | 傳統密碼世界 | FIDO2 / Passkey 世界 |
| :--- | :--- | :--- |
| **鑰匙放在哪？** | 寫在一張紙條上，每次進門唸給警衛聽（容易被偷聽、被仿冒）。 | **私鑰（Private Key）永遠焊在您的手機或電腦晶片裡，天王老子都拿不走。** |
| **開門時核驗什麼？** | 警衛比對您唸的暗號跟小抄是否一樣。 | 銀行門口有一道**數學鎖頭（公鑰 Public Key）**，只有您手機晶片蓋出的**數位簽章**才能解鎖。 |
| **生物特徵去了哪？** | 傳給伺服器比對（有指紋外洩風險）。 | **指紋與臉部辨識只在手機本機解鎖晶片，從來不傳給網路或伺服器！** |

---

## 2. 通行金鑰 (Passkey) 的三大巨頭背書

* **通行金鑰 (Passkey)**：
  就是 Apple、Google、Microsoft 全球三大科技巨頭聯合背書的 FIDO2 技術名稱。
* 它讓您的 iPhone、Android 手機或筆電（Windows Hello / Mac Touch ID），化身為比銀行保險箱更堅固的專屬隨身安全盾牌。

<div class="callout-box">
<strong>🛡️ 核心三大原則：</strong><br>
1. <strong>私鑰不出門</strong>：私鑰鎖死在硬體安全元件 (TPM / Secure Enclave)。<br>
2. <strong>公鑰不怕偷</strong>：伺服器只存公鑰，拿到公鑰在數學上無法反推私鑰。<br>
3. <strong>網域死鎖 (Anti-Phishing)</strong>：手機晶片只對合法網域蓋章，釣魚假網站永遠拿不到簽名。
</div>

---

## 3. 本系統核心架構總覽 (五大核心模組)

<pre style="background: #0f172a; color: #38bdf8; font-family: 'Cascadia Code', Consolas, 'Courier New', monospace; font-size: 15px; font-weight: 700; padding: 20px 24px; border-radius: 8px; border: 2.5px solid #0284c7; line-height: 1.45; overflow-x: auto; box-shadow: 0 6px 12px -2px rgba(0,0,0,0.3);">
                      ┌─────────────────────────────────────────┐
                      │    FIDO2 企業級無密碼身分安全中心       │
                      └─────────────────────────────────────────┘
                                           │
         ┌──────────────────┬──────────────┴─────┬──────────────────┐
         ▼                  ▼                    ▼                  ▼
   【功能一】         【功能二】           【功能三】         【功能四】
 1 秒指紋臉部登入   手機原生 QR 碼跨登    多裝置同帳號互備    離線緊急換機救援
 (免記任何密碼)    (FIDO Hybrid 藍牙)    (電腦手機各持私鑰)   (舊設備自動註銷)
                                           │
                                           ▼
                                      【功能五】
                                  特殊最高管理員後台
                                (全站憑證廢止與稽核日誌)
</pre>

---

## 3. 核心功能 ❶：1 秒指紋臉部快速登入

* **極致順暢的使用者體驗**：
  使用者在電腦前只要手指輕觸指紋辨識器，或看一眼鏡頭（Windows Hello / Face ID / Touch ID），**1 秒內完成身分鑑別與登入**。
* **完全免疫釣魚網站**：
  即使員工不小心點擊社交工程郵件，連到外觀一模一樣的駭客釣魚網站，瀏覽器底層會發現網域名稱不符，硬體晶片**絕對拒絕提供簽名**，駭客半個字也騙不到。
* **零密碼記憶負擔**：
  徹底解決員工因忘記密碼而頻繁尋求客服重設的問題，生產力大幅提升。

---

## 3. 核心功能 ❷：手機相機掃碼跨裝置登入

* **情境**：
  來到會議室公用電腦、合作夥伴辦公室或外端設備，該電腦並未登記您的個人生物特徵時。
* **操作方式**：
  1. 公用電腦螢幕跳出系統原生的 **FIDO2 Hybrid QR Code**。
  2. 拿起您自己的隨身手機，打開原生相機對準螢幕掃碼。
  3. 手機跳出生物特徵確認彈窗，按一下 Face ID / 指紋。
  4. 電腦螢幕立即完成身分授權並自動登入！
* **W3C L3 國際標準**：
  全程透過標準通訊協定，公用電腦完全接觸不到使用者的任何帳號金鑰。

---

## 3. 核心功能 ❸：多台設備綁定同一帳號

* **企業實務需求**：
  一位企業員工或主管，日常通常擁有多部工作與個人設備（例如：公司桌機、隨身筆電、iPhone、備用 Android 平板）。
* **各自持有獨立金鑰，互為備援**：
  * 使用者可以為同一帳號登記多部設備。
  * 每一部設備各自在內部晶片獨立產出專屬私鑰，**彼此完全獨立**。
  * 任一台設備故障、沒電或送修，其他已綁定設備依然能無縫登入，**達成零單點故障 (Zero Single Point of Failure)**。

---

## 3. 核心功能 ❹：離線緊急復原碼救援換機

* **傳統弱點**：
  當使用者手機掉進海裡且手邊無其他設備時，傳統系統常降級為「發送簡訊到手機門號」，容易遭受 SIM-Swap 劫持攻擊。
* **本系統的頂級資安閉環**：
  1. 初次註冊時，系統核發 **8 組高熵離線緊急復原碼**（需紙本列印保存）。
  2. 伺服器端**僅儲存加鹽雜湊 (Salted Hash)**，資料庫絕無明文。
  3. 手機遺失時，使用者憑紙本代碼登入系統進行緊急換機救援。
  4. **核驗成功後，系統自動將遺失之舊設備金鑰強制作廢 (REVOKE)**，拾獲者完全無法盜用！

---

## 3. 核心功能 ❺：特殊最高管理員後台與稽核

* **企業特權帳號治理**：
  具備最高管理員身分的專屬後台（`admin.html`），支援企業資安管理員行使關鍵治理權限：
  * **單一憑證廢止**：針對特定失竊或淘汰之單一設備實施廢止。
  * **整戶帳號作廢**：遇到員工離職、資安調查事件時，一鍵阻斷該帳號下所有設備的存取權限。
  * **誤操作恢復機制**：提供 Restore 容錯按鈕，避免人為誤按。
  * **雙頁籤安全稽核日誌 (Audit Log)**：即時收攏註冊、登入成功/失敗、簽章計數與來源 IP / User-Agent 軌跡，並支援單一使用者時間軸 (Timeline UI)。

---

## 4. 為什麼手機掃碼一定要開藍牙？——釣魚危機

許多非技術同仁常感到疑惑：
> *「我以前用 LINE、超商 App 掃描網頁 QR Code 登入，從來不需要開藍牙，為什麼 FIDO2 規範規定手機跟電腦都一定要開啟藍牙？」*

### 傳統網頁 QR Code 的致命危險（QR 釣魚截圖轉發）
1. 駭客人在國外架設假網站，假網站即時連線正版網站取得一個 QR Code。
2. 駭客將 QR Code 截圖傳給您（例如騙您：「掃碼領取禮券或簽核文件」）。
3. 您在台灣拿手機一掃，因為手機只要有網路就能連線，您在手機上按了確認。
4. **結果：身處國外的駭客電腦瞬間登入您的帳戶！您被隔空盜用！**

---

## 4. FIDO Hybrid 的物理防護：藍牙近場信標

FIDO 聯盟在制定 W3C WebAuthn Level 3 標準時，強制加入了**「藍牙近場探測 (Proximity Check)」**：

<pre style="background: #0f172a; color: #38bdf8; font-family: 'Cascadia Code', Consolas, 'Courier New', monospace; font-size: 15px; font-weight: 700; padding: 20px 24px; border-radius: 8px; border: 2.5px solid #0284c7; line-height: 1.5; overflow-x: auto; box-shadow: 0 6px 12px -2px rgba(0,0,0,0.3);">
 [ 您的電腦螢幕 ]                                [ 您的手機 ]
 (顯示 QR Code)                                  (相機掃碼)
        │                                             │
        └─── [ 藍牙 BLE 微弱訊號 (探測半徑約 5 公尺) ] ───┘
                           │
                 【確認雙方確實在同一個房間】
                           │
                 【若距離過遠 (如千里之外)】
                 ==> 立即判定遭釣魚，強制中斷！
</pre>

* **手機掃電腦螢幕**：必須確認「操作者本人就坐在電腦正前方」，因此雙方必須開藍牙。
* **直接在手機瀏覽器登入** 或 **在電腦用 Windows Hello 登入**：**完全不需要開藍牙！**

---

## 5. 特殊最高管理員 (ADMIN) 身分機制

* **誰是 ADMIN 特殊管理員？**
  * 資料庫 `users` 表格的 `role` 欄位預設為 `null`（代表所有一般註冊用戶）。
  * 只有在受控內部環境中，由資料庫管理員手動指定 `role = 'ADMIN'` 的特殊帳號，才具備最高管理員身分。
* **強制的存取控制防護**：
  * 一般使用者登入看不見後台按鈕。
  * 若惡意嘗試直接輸入網址訪問，後端 API 均會檢驗身分並回傳 **HTTP 403 Forbidden 嚴格阻斷**。
  * 前端同時具備動態身分導航，確保非 ADMIN 帳號無權檢視。

---

## 5. 雙頁籤核心治理功能

<pre style="background: #0f172a; color: #38bdf8; font-family: 'Cascadia Code', Consolas, 'Courier New', monospace; font-size: 14px; font-weight: 700; padding: 18px 20px; border-radius: 8px; border: 2.5px solid #0284c7; line-height: 1.45; overflow-x: auto; box-shadow: 0 6px 12px -2px rgba(0,0,0,0.3);">
┌────────────────────────────────────────────────────────────────────────┐
│                        管理員核心治理權力                              │
├────────────────────────────────┬───────────────────────────────────────┤
│ 1. 帳號與 Passkey 憑證管理     │ • 全站儀表板（註冊數、設備數、廢止數）。│
│    (分頁一)                    │ • 各帳號設備履歷（綁定數量、名稱、狀態）。│
│                                │ • 憑證撤銷控制（單一廢止、整戶作廢、復原）。│
│                                │ • [ 📜 紀錄 ] 彈出單一使用者專屬時間軸。 │
├────────────────────────────────┼───────────────────────────────────────┤
│ 2. 全系統安全稽核日誌          │ • 集中化追蹤所有帳號之關鍵生命週期事件。│
│    (分頁二)                    │ • 記錄 IP、User-Agent、動作類型與詳細訊息。│
│                                │ • 快速分類按鈕（全部、登入、註冊、管理）。│
│                                │ • 即時關鍵字搜尋與筆數限制（50~500 筆）。│
└────────────────────────────────┴───────────────────────────────────────┘
</pre>

---

## 5. 全維度安全事件審計追蹤

系統對全站每一筆關鍵事件進行毫秒級自動審計紀錄：

* <span class="badge badge-success">REGISTER</span> **Passkey 憑證註冊**：記錄註冊時間、設備暱稱與演算法。
* <span class="badge badge-primary">LOGIN_SUCCESS</span> **成功登入驗證**：記錄當次簽章計數值與來源 IP。
* <span class="badge" style="background:#fed7d7;color:#991b1b;border:2px solid #ef4444;">LOGIN_FAIL</span> **登入失敗與警報**：詳細記錄失敗原因或疑似複製攻擊警報。
* <span class="badge badge-primary">REVOKE / RESTORE</span> **憑證作廢與恢復**：追蹤管理員的撤銷與啟用歷程。
* <span class="badge badge-success">RECOVERY_RESET</span> **離線緊急換機**：記錄使用者憑復原碼重設事件。

---

## 6. 換手機、手機遺失壞掉怎麼辦？——離線救援

非技術同仁最常擔心的問題：
> *「如果完全沒有密碼，那萬一我的手機掉進水裡壞了、或者遺失了，我不就永遠進不去系統了？」*

### 災難救援換機三步驟：
1. **初次註冊時**：
   系統單次發放並顯示 **8 組高熵離線緊急復原碼**（格式如 `x8k2-9pLm-7vQa-4z1w`），資料庫僅存加鹽雜湊，明文不在線上保留。
2. **手機遺失時**：
   使用者拿出紙本復原碼，在首頁點選「使用離線緊急復原碼救援換機」，輸入任一組未使用的代碼。

---

## 6. 救援換機資安閉環：舊機強制作廢

### 救援換機安全閉環續篇：
3. **安全閉環（自動廢止舊機）**：
   * 系統核對加鹽雜湊成功後，放行本次救援登入。
   * **同時自動將遺失的舊手機金鑰標記為作廢 (`REVOKED`)**，拾獲舊手機的人即使破解手機密碼，也無法再登入系統！
   * 系統引導使用者立即為新拿到的手機或電腦綁定全新 Passkey。

<div class="warning-box">
<strong>🔒 零降級保護原則：</strong><br>
本系統徹底封鎖傳統「發簡訊重設密碼」之安全漏洞。救援碼單次核銷即作廢，確保災難換機流程具備不可否認性與最高安全防線。
</div>

---

## 7. 常見疑問解答 (FAQ 1/4)：生物特徵疑慮

### Q1：伺服器資料庫如果被駭客偷走，我的指紋或臉部照片會外洩嗎？
> **A：絕對不會！百分之百不可能！**
> FIDO2 的核心設計原則是「生物特徵絕不離開設備」。
> 1. 您的指紋與 Face ID 只在您手機或電腦晶片內部進行比對。
> 2. 晶片比對通過後，僅用內部數學私鑰對隨機文字簽章後發給伺服器。
> 3. 伺服器只儲存公開金鑰，**伺服器從頭到尾根本沒有、也無法取得您的任何指紋或臉部影像資料**！

---

## 7. 常見疑問解答 (FAQ 2/4)：資料庫被「脫褲」

### Q2：如果伺服器資料庫不幸遭駭客完全偷走（脫褲），攻擊者能偽造登入嗎？
> **A：絕對無法直接偽造登入！**
> 1. **私鑰從不留在伺服器**：伺服器僅有「公鑰」與「憑證代號」。私鑰鎖在硬體晶片內，數學上拿到公鑰無法反推私鑰，更無法簽出合法登入印章。
> 2. **每次登入都是全新隨機挑戰碼 (Challenge)**：每次登入由伺服器派發 32-byte 隨機數，一次性且限時逾期，攻擊者攔截舊封包無法重放。
> 3. **網域死鎖 (Origin Binding)**：晶片只認正版網域。駭客即使持有公鑰資料庫，架設山寨網站也永遠騙不到手機晶片簽名。

---

## 7. 常見疑問解答 (FAQ 3/4)：離職與誤操作

### Q3：員工離職了，他手機上的通行金鑰還能登入公司嗎？
> **A：完全不能！**
> 管理員只要進入 `admin.html` 後台，找到該離職員工帳號點擊「整戶廢止」，資料庫即刻將該員工所有憑證狀態標記為 `REVOKED`。此後該員工即使點擊手機 Face ID，伺服器一律拒絕連線。

### Q4：不小心按了「整戶廢止」，還救得回來嗎？
> **A：可以！**
> 管理員後台特別設計了「重新啟用 (Restore)」容錯按鈕，若經查核確認為誤操作，管理員可一鍵將已作廢之憑證重新恢復為 `ACTIVE`。

---

## 7. 常見疑問解答 (FAQ 4/4)：認證、快取與環境

### Q5：系統有通過國際認證測試嗎？
> **A：有的！** 本專案內建 FIDO 官方規格測試套件（`conformance.html`），全數通過官方定義的 **24 項核心 Conformance 測試案例，通過率 100%**。

### Q6：登出後按「返回上一頁」，會看到個人資訊嗎？
> **A：絕對不會！** 系統後端吐出 `Cache-Control: no-store`，前端監聽 `pageshow` 快取喚醒，登出後按上一頁在 **0 毫秒瞬間強制清空並切回登入框**，完全符合金管會金融資安指引與 OWASP 標準。

### Q7：未來系統切換到正式環境或雲端（AWS/GCP），需要工程師大改程式嗎？
> **A：完全不需要！只需修改 1 個設定檔 (`.env`) 即可一秒無痛切換！** 未來上線正式環境只需替換正式網域名稱 (URL & Origin) 與資料庫位置，前端與後端將全自動適應，完全不需重新編譯或改寫程式。

---

## 8. 法規遵循與國際資安標準效益

導入本套 FIDO2 無密碼身分安全中心，對企業具備實質且顯著的法規合規與商業競爭力：

| 國際與國內標準 | 規範要求 | 本系統達成指標 |
| :--- | :--- | :--- |
| **金管會金融資安指引** | 強化雙因子認證、防止公私鑰遭中間人截獲。 | **100% 符合**。私鑰硬體隔離，徹底淘汰傳統密碼。 |
| **NIST SP 800-63B** | 數位身分指引最高等級 **AAL3**（最高保證等級）。 | 達成硬體非對稱簽章、抗釣魚驗證（Phishing-Resistant）。 |
| **CISA 零信任架構** | 美國網路安全局零信任成熟度模型。 | 符合「永不信任、始終驗證」標準，以公鑰密碼學取代對稱金鑰。 |
| **ISO 27001 / SOC 2** | 身分存取管理 (IAM) 與特權帳號治理要求。 | 具備完備的最高權限管理員 (ADMIN) 稽核、日誌審計與憑證撤銷。 |

---

<!-- _class: lead -->
<div style="background: linear-gradient(135deg, #0a1f38 0%, #163e68 100%); color: #ffffff; padding: 42px 30px; border-radius: 12px; text-align: center; box-shadow: 0 10px 20px -3px rgba(0,0,0,0.3);">
  <h1 style="color: #ffffff !important; font-size: 34px; font-weight: 800; margin-bottom: 14px; border: none; text-shadow: 0 2px 4px rgba(0,0,0,0.5);">感謝聆聽 ｜ 歡迎提問交流</h1>
  <h2 style="color: #60a5fa !important; font-size: 22px; font-weight: 700; margin-bottom: 24px; border: none; text-shadow: 0 1px 3px rgba(0,0,0,0.5);">FIDO2 / WebAuthn 企業級無密碼身分安全中心</h2>
  <p style="color: #f1f5f9 !important; font-size: 17px; margin: 6px 0; font-weight: 600;"><strong>專案成果：</strong> 24/24 官方 Conformance 測試 100% 通過</p>
  <p style="color: #f1f5f9 !important; font-size: 17px; margin: 6px 0; font-weight: 600;"><strong>架構特性：</strong> 雲原生 .env 環境抽離 ｜ 零密碼 ｜ 抗中間人釣魚 ｜ 離線災難救援換機</p>
  <p style="color: #cbd5e1 !important; font-size: 16px; margin: 6px 0;"><strong>安全標準：</strong> 金管會資安指引 ｜ NIST AAL3 ｜ CISA 零信任架構</p>
</div>
