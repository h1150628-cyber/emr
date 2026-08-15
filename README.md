#<!DOCTYPE html>
<html lang="zh-Hant">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>MyMed Passport｜多國語言隨身電子病歷</title>
<style>
:root{
  --blue:#1e88e5; --blue2:#42a5f5; --sky:#eaf6ff; --ice:#f6fbff;
  --navy:#16324f; --text:#26384a; --muted:#718399; --white:#fff;
  --line:#dceaf5; --shadow:0 18px 45px rgba(30,96,150,.12);
  --radius:22px;
}
*{box-sizing:border-box}
html{scroll-behavior:smooth}
body{
  margin:0;font-family:Inter,"Noto Sans TC","Noto Sans",Arial,sans-serif;
  color:var(--text);background:linear-gradient(145deg,#fafdff 0%,#edf8ff 45%,#f7fbff 100%);
}
button,input,textarea,select{font:inherit}
button{cursor:pointer}
.topbar{
  position:sticky;top:0;z-index:20;backdrop-filter:blur(14px);
  background:rgba(255,255,255,.88);border-bottom:1px solid rgba(220,234,245,.8);
  padding:12px 5vw;display:flex;align-items:center;justify-content:space-between;gap:18px
}
.brand{display:flex;align-items:center;gap:12px;font-weight:800;color:var(--navy)}
.logo{width:42px;height:42px;border-radius:13px;background:linear-gradient(135deg,var(--blue),#8bd4ff);
display:grid;place-items:center;color:white;font-size:23px;box-shadow:0 8px 18px rgba(30,136,229,.22)}
.lang{border:1px solid var(--line);background:white;border-radius:12px;padding:9px 12px;color:var(--navy);outline:none}
.hero{max-width:1200px;margin:0 auto;padding:68px 24px 35px;display:grid;grid-template-columns:1.2fr .8fr;gap:32px;align-items:center}
.eyebrow{display:inline-flex;gap:8px;align-items:center;padding:8px 12px;border-radius:999px;background:#e2f3ff;color:#1976c9;font-size:13px;font-weight:700}
h1{font-size:clamp(38px,5vw,66px);line-height:1.05;margin:18px 0 16px;color:var(--navy);letter-spacing:-1.8px}
.hero p{font-size:18px;line-height:1.8;color:var(--muted);max-width:690px}
.hero-actions{display:flex;gap:12px;flex-wrap:wrap;margin-top:25px}
.btn{border:0;border-radius:14px;padding:13px 18px;font-weight:800}
.btn.primary{background:var(--blue);color:#fff;box-shadow:0 10px 22px rgba(30,136,229,.22)}
.btn.secondary{background:white;color:var(--blue);border:1px solid #cfe7f7}
.health-card{background:rgba(255,255,255,.85);border:1px solid var(--line);border-radius:28px;padding:24px;box-shadow:var(--shadow);position:relative;overflow:hidden}
.health-card:before{content:"";position:absolute;width:170px;height:170px;background:#d9f1ff;border-radius:50%;right:-55px;top:-65px}
.card-title{display:flex;justify-content:space-between;align-items:center;margin-bottom:18px}
.status{font-size:12px;color:#168451;background:#e4f8ee;border-radius:999px;padding:6px 9px;font-weight:800}
.profile{display:flex;gap:15px;align-items:center;padding:15px;border-radius:18px;background:var(--ice)}
.avatar{width:58px;height:58px;border-radius:18px;background:linear-gradient(135deg,#80cfff,#d8f3ff);display:grid;place-items:center;font-size:25px}
.profile strong{display:block;color:var(--navy);font-size:17px}
.profile small{color:var(--muted)}
.mini-grid{display:grid;grid-template-columns:1fr 1fr;gap:10px;margin-top:12px}
.mini{padding:13px;border:1px solid var(--line);border-radius:15px;background:#fff}
.mini b{display:block;font-size:18px;color:var(--navy)}
.mini span{font-size:12px;color:var(--muted)}
.wrap{max-width:1200px;margin:auto;padding:20px 24px 70px}
.notice{padding:16px 18px;border-radius:17px;background:#e8f6ff;border:1px solid #cce8f8;color:#35647e;margin-bottom:22px;line-height:1.65}
.grid{display:grid;grid-template-columns:repeat(3,1fr);gap:16px}
.section-card{background:rgba(255,255,255,.9);border:1px solid var(--line);border-radius:var(--radius);padding:22px;box-shadow:0 8px 30px rgba(50,110,150,.06)}
.section-card h2{font-size:18px;margin:0 0 8px;color:var(--navy)}
.section-card p{font-size:13px;color:var(--muted);line-height:1.6;margin:0 0 17px}
.icon{width:42px;height:42px;border-radius:13px;background:#e8f6ff;color:var(--blue);display:grid;place-items:center;font-size:20px;margin-bottom:14px}
.form-grid{display:grid;grid-template-columns:repeat(2,1fr);gap:12px}
label{font-size:12px;color:#5f7285;font-weight:700;display:block;margin-bottom:6px}
input,textarea,select{width:100%;border:1px solid var(--line);border-radius:12px;padding:11px 12px;background:#fbfdff;color:var(--text);outline:none}
input:focus,textarea:focus,select:focus{border-color:#82c9f2;box-shadow:0 0 0 3px #e5f5ff}
textarea{min-height:92px;resize:vertical}
.full{grid-column:1/-1}
.list{display:flex;flex-direction:column;gap:10px}
.row{display:flex;justify-content:space-between;gap:10px;padding:12px;border:1px solid var(--line);border-radius:13px;background:#fcfeff}
.row strong{color:var(--navy);font-size:14px}
.row span{font-size:12px;color:var(--muted)}
.footer{padding:28px 24px;text-align:center;color:#8092a4;font-size:12px}
.toast{position:fixed;right:22px;bottom:22px;background:#16324f;color:white;padding:13px 16px;border-radius:13px;box-shadow:var(--shadow);opacity:0;transform:translateY(15px);transition:.25s;z-index:50}
.toast.show{opacity:1;transform:translateY(0)}
@media(max-width:900px){.hero{grid-template-columns:1fr}.grid{grid-template-columns:1fr 1fr}}
@media(max-width:620px){.topbar{padding:10px 16px}.hero,.wrap{padding-left:16px;padding-right:16px}.grid{grid-template-columns:1fr}.form-grid{grid-template-columns:1fr}.hero{padding-top:42px}}
</style>
</head>
<body>
<header class="topbar">
  <div class="brand"><div class="logo">✚</div><span data-i18n="brand">MyMed Passport</span></div>
  <select class="lang" id="language" aria-label="Language">
    <option value="zh">繁體中文</option><option value="en">English</option>
    <option value="ja">日本語</option><option value="ko">한국어</option>
    <option value="vi">Tiếng Việt</option>
  </select>
</header>

<section class="hero">
  <div>
    <span class="eyebrow">✦ <span data-i18n="eyebrow">Personal Health Passport</span></span>
    <h1 data-i18n="heroTitle">你的健康資料，<br>隨身帶著走。</h1>
    <p data-i18n="heroText">一份為跨國旅行、就醫與緊急狀況設計的個人電子病歷介面。集中管理重要健康資訊，並可快速切換多國語言。</p>
    <div class="hero-actions">
      <button class="btn primary" onclick="scrollToForm()" data-i18n="start">開始填寫病歷</button>
      <button class="btn secondary" onclick="exportData()" data-i18n="export">匯出健康資料</button>
    </div>
  </div>
  <div class="health-card">
    <div class="card-title"><strong data-i18n="overview">健康摘要</strong><span class="status" data-i18n="ready">資料就緒</span></div>
    <div class="profile"><div class="avatar">👤</div><div><strong id="previewName">Your Name</strong><small data-i18n="profileHint">個人健康檔案</small></div></div>
    <div class="mini-grid">
      <div class="mini"><b id="bloodPreview">—</b><span data-i18n="blood">血型</span></div>
      <div class="mini"><b id="allergyPreview">—</b><span data-i18n="allergy">過敏</span></div>
      <div class="mini"><b id="medPreview">0</b><span data-i18n="meds">目前用藥</span></div>
      <div class="mini"><b id="surgeryPreview">0</b><span data-i18n="surgeries">手術紀錄</span></div>
    </div>
  </div>
</section>

<main class="wrap" id="form">
  <div class="notice" data-i18n="privacy">🔒 隱私提醒：這是一個純前端靜態範例。資料只存在於你的瀏覽器記憶體中，不會自動上傳伺服器。正式使用時仍應加入加密、身分驗證、備份與醫療資料合規機制。</div>

  <div class="grid">
    <section class="section-card">
      <div class="icon">🪪</div><h2 data-i18n="personalTitle">個人基本資料</h2><p data-i18n="personalDesc">讓醫療人員快速辨識你的基本資訊。</p>
      <div class="form-grid">
        <div><label data-i18n="name">姓名</label><input id="name" placeholder="Your name"></div>
        <div><label data-i18n="dob">出生日期</label><input id="dob" type="date"></div>
        <div><label data-i18n="sex">生理性別</label><select><option>—</option><option>Female</option><option>Male</option><option>Other</option></select></div>
        <div><label data-i18n="bloodType">血型</label><select id="blood"><option>—</option><option>A+</option><option>A-</option><option>B+</option><option>B-</option><option>AB+</option><option>AB-</option><option>O+</option><option>O-</option></select></div>
        <div class="full"><label data-i18n="idNumber">身分／護照號碼（選填）</label><input placeholder="Optional"></div>
        <div class="full"><label data-i18n="emergency">緊急聯絡人</label><input placeholder="Name / Phone / Relationship"></div>
      </div>
    </section>

    <section class="section-card">
      <div class="icon">🩺</div><h2 data-i18n="historyTitle">疾病／病史</h2><p data-i18n="historyDesc">記錄目前疾病與過去重要病史。</p>
      <label data-i18n="conditions">已知疾病／慢性病</label><textarea placeholder="例如：高血壓、氣喘、糖尿病…"></textarea>
      <label data-i18n="past">重大過去病史</label><textarea placeholder="診斷、年份、治療結果…"></textarea>
    </section>

    <section class="section-card">
      <div class="icon">🧬</div><h2 data-i18n="familyTitle">家族史</h2><p data-i18n="familyDesc">協助醫療人員了解可能的遺傳或家族疾病風險。</p>
      <textarea placeholder="父母、兄弟姊妹、祖父母等的重要疾病史…"></textarea>
      <label data-i18n="familyNote">家族中是否有遺傳性疾病</label>
      <input placeholder="疾病名稱／親屬／備註">
    </section>

    <section class="section-card">
      <div class="icon">🏥</div><h2 data-i18n="surgeryTitle">手術／住院史</h2><p data-i18n="surgeryDesc">包含手術、住院、麻醉或重大醫療處置。</p>
      <div class="list">
        <div class="row"><div><strong data-i18n="surgeryExample">手術紀錄</strong><span> — 2023 / Hospital</span></div><button onclick="removeRow(this)">×</button></div>
        <button class="btn secondary" onclick="addRow(this)" data-i18n="add">＋ 新增紀錄</button>
      </div>
    </section>

    <section class="section-card">
      <div class="icon">💊</div><h2 data-i18n="medTitle">用藥史</h2><p data-i18n="medDesc">處方藥、非處方藥、保健品與曾發生的藥物不良反應。</p>
      <div class="list">
        <div class="row"><div><strong data-i18n="medExample">藥物名稱</strong><span> — 劑量／頻率</span></div><button onclick="removeRow(this)">×</button></div>
        <button class="btn secondary" onclick="addRow(this)" data-i18n="add">＋ 新增藥物</button>
      </div>
    </section>

    <section class="section-card">
      <div class="icon">⚠️</div><h2 data-i18n="allergyTitle">過敏與不良反應</h2><p data-i18n="allergyDesc">這是急診與跨國就醫時非常重要的資訊。</p>
      <label data-i18n="drugAllergy">藥物過敏</label><textarea placeholder="藥物名稱／反應"></textarea>
      <label data-i18n="otherAllergy">食物、環境或其他過敏</label><textarea placeholder="例如：花生、乳膠、花粉…"></textarea>
    </section>

    <section class="section-card">
      <div class="icon">💉</div><h2 data-i18n="vaccineTitle">疫苗／預防接種</h2><p data-i18n="vaccineDesc">方便旅遊與醫療評估時快速查閱。</p>
      <textarea placeholder="疫苗名稱／日期／劑次／備註…"></textarea>
    </section>

    <section class="section-card">
      <div class="icon">🧪</div><h2 data-i18n="labTitle">重要檢查／檢驗</h2><p data-i18n="labDesc">保存值得長期追蹤的檢查結果與日期。</p>
      <textarea placeholder="檢查名稱／日期／結果／醫師備註…"></textarea>
    </section>

    <section class="section-card">
      <div class="icon">🫀</div><h2 data-i18n="lifestyleTitle">生活與健康習慣</h2><p data-i18n="lifestyleDesc">補充醫療人員可能需要知道的背景資訊。</p>
      <textarea placeholder="吸菸、飲酒、運動、飲食、睡眠等…"></textarea>
    </section>

    <section class="section-card">
      <div class="icon">📏</div><h2 data-i18n="vitalsTitle">重要健康數值</h2><p data-i18n="vitalsDesc">可記錄平時基準值，方便就醫比較。</p>
      <div class="form-grid">
        <div><label>Height / 身高</label><input placeholder="cm"></div>
        <div><label>Weight / 體重</label><input placeholder="kg"></div>
        <div><label>Blood Pressure / 血壓</label><input placeholder="120/80 mmHg"></div>
        <div><label>Pulse / 脈搏</label><input placeholder="bpm"></div>
      </div>
    </section>

    <section class="section-card">
      <div class="icon">🧠</div><h2 data-i18n="specialTitle">特殊醫療資訊</h2><p data-i18n="specialDesc">可補充醫療人員容易忽略但很重要的資訊。</p>
      <textarea placeholder="植入物、義肢、懷孕相關資訊、特殊醫療需求、器官捐贈意願、宗教／照護偏好等…"></textarea>
    </section>

    <section class="section-card">
      <div class="icon">📄</div><h2 data-i18n="documentsTitle">醫療文件索引</h2><p data-i18n="documentsDesc">記錄影像、報告或病歷文件的位置；正式版可串接安全文件儲存。</p>
      <textarea placeholder="文件名稱／日期／醫院／備註…"></textarea>
    </section>
  </div>
</main>

<footer class="footer">
  <span data-i18n="footer">MyMed Passport · 靜態前端示範 · 請勿將此範例視為醫療診斷或正式醫療資訊系統</span>
</footer>
<div class="toast" id="toast"></div>

<script>
const translations={
zh:{brand:"MyMed Passport",eyebrow:"Personal Health Passport",heroTitle:"你的健康資料，<br>隨身帶著走。",heroText:"一份為跨國旅行、就醫與緊急狀況設計的個人電子病歷介面。集中管理重要健康資訊，並可快速切換多國語言。",start:"開始填寫病歷",export:"匯出健康資料",overview:"健康摘要",ready:"資料就緒",profileHint:"個人健康檔案",blood:"血型",allergy:"過敏",meds:"目前用藥",surgeries:"手術紀錄",privacy:"🔒 隱私提醒：這是一個純前端靜態範例。資料只存在於你的瀏覽器記憶體中，不會自動上傳伺服器。正式使用時仍應加入加密、身分驗證、備份與醫療資料合規機制。",personalTitle:"個人基本資料",personalDesc:"讓醫療人員快速辨識你的基本資訊。",name:"姓名",dob:"出生日期",sex:"生理性別",bloodType:"血型",idNumber:"身分／護照號碼（選填）",emergency:"緊急聯絡人",historyTitle:"疾病／病史",historyDesc:"記錄目前疾病與過去重要病史。",conditions:"已知疾病／慢性病",past:"重大過去病史",familyTitle:"家族史",familyDesc:"協助醫療人員了解可能的遺傳或家族疾病風險。",familyNote:"家族中是否有遺傳性疾病",surgeryTitle:"手術／住院史",surgeryDesc:"包含手術、住院、麻醉或重大醫療處置。",surgeryExample:"手術紀錄",medTitle:"用藥史",medDesc:"處方藥、非處方藥、保健品與曾發生的藥物不良反應。",medExample:"藥物名稱",allergyTitle:"過敏與不良反應",allergyDesc:"這是急診與跨國就醫時非常重要的資訊。",drugAllergy:"藥物過敏",otherAllergy:"食物、環境或其他過敏",vaccineTitle:"疫苗／預防接種",vaccineDesc:"方便旅遊與醫療評估時快速查閱。",labTitle:"重要檢查／檢驗",labDesc:"保存值得長期追蹤的檢查結果與日期。",lifestyleTitle:"生活與健康習慣",lifestyleDesc:"補充醫療人員可能需要知道的背景資訊。",vitalsTitle:"重要健康數值",vitalsDesc:"可記錄平時基準值，方便就醫比較。",specialTitle:"特殊醫療資訊",specialDesc:"可補充醫療人員容易忽略但很重要的資訊。",documentsTitle:"醫療文件索引",documentsDesc:"記錄影像、報告或病歷文件的位置；正式版可串接安全文件儲存。",add:"＋ 新增紀錄",footer:"MyMed Passport · 靜態前端示範 · 請勿將此範例視為醫療診斷或正式醫療資訊系統"},
en:{brand:"MyMed Passport",eyebrow:"Personal Health Passport",heroTitle:"Your health data,<br>wherever you go.",heroText:"A personal medical record interface designed for international travel, healthcare visits, and emergencies. Organize essential health information and switch languages instantly.",start:"Start Medical Record",export:"Export Health Data",overview:"Health Summary",ready:"Ready",profileHint:"Personal health profile",blood:"Blood Type",allergy:"Allergies",meds:"Medications",surgeries:"Surgeries",privacy:"🔒 Privacy note: This is a static front-end demo. Data stays in your browser and is not uploaded automatically. A production system needs encryption, authentication, backups, and healthcare compliance.",personalTitle:"Personal Information",personalDesc:"Basic information for quick identification.",name:"Full Name",dob:"Date of Birth",sex:"Sex",bloodType:"Blood Type",idNumber:"ID / Passport Number (optional)",emergency:"Emergency Contact",historyTitle:"Medical History",historyDesc:"Current conditions and significant past history.",conditions:"Known Conditions / Chronic Diseases",past:"Significant Past History",familyTitle:"Family History",familyDesc:"Relevant hereditary or family disease risks.",familyNote:"Hereditary diseases in family",surgeryTitle:"Surgery / Hospitalization",surgeryDesc:"Surgeries, hospital stays, anesthesia, and major procedures.",surgeryExample:"Surgery Record",medTitle:"Medication History",medDesc:"Prescription drugs, OTC medicines, supplements, and adverse reactions.",medExample:"Medication",allergyTitle:"Allergies & Adverse Reactions",allergyDesc:"Critical information for emergency and international care.",drugAllergy:"Drug Allergies",otherAllergy:"Food, Environmental or Other Allergies",vaccineTitle:"Vaccinations",vaccineDesc:"Useful for travel and clinical assessment.",labTitle:"Important Tests / Labs",labDesc:"Long-term test results and dates.",lifestyleTitle:"Lifestyle & Habits",lifestyleDesc:"Background information useful to healthcare professionals.",vitalsTitle:"Vital Health Metrics",vitalsDesc:"Baseline values for comparison during care.",specialTitle:"Special Medical Information",specialDesc:"Important details that may otherwise be overlooked.",documentsTitle:"Medical Document Index",documentsDesc:"Index reports or records; a production version can connect to secure storage.",add:"＋ Add Record",footer:"MyMed Passport · Static front-end demo · Not a medical diagnosis or production medical record system"},
ja:{brand:"MyMed Passport",eyebrow:"パーソナル健康パスポート",heroTitle:"あなたの健康情報を、<br>いつでも持ち歩く。",heroText:"海外旅行、受診、緊急時のための個人電子カルテ・インターフェース。重要な健康情報をまとめ、多言語をすぐに切り替えられます。",start:"カルテを入力",export:"健康データを出力",overview:"健康サマリー",ready:"準備完了",profileHint:"個人健康プロフィール",blood:"血液型",allergy:"アレルギー",meds:"服用薬",surgeries:"手術記録",privacy:"🔒 プライバシー：これは静的フロントエンドのデモです。データはブラウザ内にのみ保持され、自動送信されません。本番環境では暗号化、認証、バックアップ、医療情報規制への対応が必要です。",personalTitle:"基本情報",personalDesc:"医療スタッフがすぐ確認できる基本情報。",name:"氏名",dob:"生年月日",sex:"性別",bloodType:"血液型",idNumber:"身分証／パスポート番号（任意）",emergency:"緊急連絡先",historyTitle:"病歴",historyDesc:"現在の疾患と重要な既往歴。",conditions:"既知の疾患／慢性疾患",past:"重要な既往歴",familyTitle:"家族歴",familyDesc:"遺伝性・家族性疾患のリスク。",familyNote:"家族内の遺伝性疾患",surgeryTitle:"手術／入院歴",surgeryDesc:"手術、入院、麻酔、重大な処置。",surgeryExample:"手術記録",medTitle:"服薬歴",medDesc:"処方薬、市販薬、サプリメント、副作用。",medExample:"薬剤名",allergyTitle:"アレルギー・副作用",allergyDesc:"救急・海外受診で重要な情報です。",drugAllergy:"薬剤アレルギー",otherAllergy:"食物・環境・その他のアレルギー",vaccineTitle:"予防接種",vaccineDesc:"旅行や診療時にすぐ確認できます。",labTitle:"重要な検査",labDesc:"長期的に追跡する検査結果と日付。",lifestyleTitle:"生活習慣",lifestyleDesc:"医療スタッフに役立つ背景情報。",vitalsTitle:"健康指標",vitalsDesc:"受診時の比較に使える基準値。",specialTitle:"特別な医療情報",specialDesc:"見落とされやすい重要情報。",documentsTitle:"医療書類インデックス",documentsDesc:"検査報告などを記録。本番版では安全な保管機能と連携できます。",add:"＋ 記録を追加",footer:"MyMed Passport · 静的フロントエンドデモ · 医療診断・本番用医療システムではありません"},
ko:{brand:"MyMed Passport",eyebrow:"개인 건강 패스포트",heroTitle:"건강 정보를<br>언제 어디서나.",heroText:"해외여행, 진료, 응급상황을 위한 개인 전자병력 인터페이스입니다. 중요한 건강정보를 정리하고 여러 언어로 빠르게 전환할 수 있습니다.",start:"병력 작성 시작",export:"건강 데이터 내보내기",overview:"건강 요약",ready:"준비 완료",profileHint:"개인 건강 프로필",blood:"혈액형",allergy:"알레르기",meds:"복용 약",surgeries:"수술 기록",privacy:"🔒 개인정보 안내: 정적 프론트엔드 데모입니다. 데이터는 브라우저에만 유지되며 자동 업로드되지 않습니다. 실제 서비스에는 암호화, 인증, 백업 및 의료정보 규정 준수가 필요합니다.",personalTitle:"기본 개인정보",personalDesc:"의료진이 빠르게 확인할 수 있는 기본 정보입니다.",name:"이름",dob:"생년월일",sex:"성별",bloodType:"혈액형",idNumber:"신분증／여권 번호 (선택)",emergency:"응급 연락처",historyTitle:"질병／병력",historyDesc:"현재 질환과 중요한 과거 병력입니다.",conditions:"알려진 질환／만성질환",past:"중요 과거 병력",familyTitle:"가족력",familyDesc:"유전성 또는 가족성 질환 위험 정보입니다.",familyNote:"가족의 유전성 질환",surgeryTitle:"수술／입원력",surgeryDesc:"수술, 입원, 마취 및 주요 처치입니다.",surgeryExample:"수술 기록",medTitle:"복약력",medDesc:"처방약, 일반의약품, 보충제 및 이상반응입니다.",medExample:"약물명",allergyTitle:"알레르기 및 이상반응",allergyDesc:"응급 및 해외 진료에서 매우 중요한 정보입니다.",drugAllergy:"약물 알레르기",otherAllergy:"음식·환경·기타 알레르기",vaccineTitle:"예방접종",vaccineDesc:"여행과 진료 시 빠르게 확인할 수 있습니다.",labTitle:"중요 검사／검진",labDesc:"장기 추적이 필요한 검사 결과와 날짜입니다.",lifestyleTitle:"생활습관",lifestyleDesc:"의료진에게 도움이 되는 생활 배경 정보입니다.",vitalsTitle:"주요 건강 수치",vitalsDesc:"진료 시 비교할 수 있는 평소 기준값입니다.",specialTitle:"특수 의료 정보",specialDesc:"놓치기 쉬운 중요한 정보를 추가합니다.",documentsTitle:"의료 문서 색인",documentsDesc:"검사 보고서 등을 기록합니다. 실제 버전은 보안 저장소와 연동할 수 있습니다.",add:"＋ 기록 추가",footer:"MyMed Passport · 정적 프론트엔드 데모 · 의료 진단 또는 실제 의료정보 시스템이 아닙니다"},
vi:{brand:"MyMed Passport",eyebrow:"Hộ chiếu sức khỏe cá nhân",heroTitle:"Thông tin sức khỏe của bạn,<br>luôn bên bạn.",heroText:"Giao diện hồ sơ bệnh án cá nhân dành cho du lịch quốc tế, khám chữa bệnh và tình huống khẩn cấp. Quản lý thông tin quan trọng và chuyển đổi ngôn ngữ nhanh chóng.",start:"Bắt đầu hồ sơ",export:"Xuất dữ liệu sức khỏe",overview:"Tóm tắt sức khỏe",ready:"Sẵn sàng",profileHint:"Hồ sơ sức khỏe cá nhân",blood:"Nhóm máu",allergy:"Dị ứng",meds:"Thuốc đang dùng",surgeries:"Lịch sử phẫu thuật",privacy:"🔒 Lưu ý quyền riêng tư: Đây là bản demo frontend tĩnh. Dữ liệu chỉ nằm trong trình duyệt và không tự động tải lên máy chủ. Bản chính thức cần mã hóa, xác thực, sao lưu và tuân thủ quy định dữ liệu y tế.",personalTitle:"Thông tin cá nhân",personalDesc:"Thông tin cơ bản để nhân viên y tế nhận diện nhanh.",name:"Họ và tên",dob:"Ngày sinh",sex:"Giới tính",bloodType:"Nhóm máu",idNumber:"CMND / Hộ chiếu (tùy chọn)",emergency:"Liên hệ khẩn cấp",historyTitle:"Tiền sử bệnh",historyDesc:"Bệnh hiện tại và tiền sử quan trọng.",conditions:"Bệnh đã biết / Bệnh mạn tính",past:"Tiền sử bệnh quan trọng",familyTitle:"Tiền sử gia đình",familyDesc:"Nguy cơ bệnh di truyền hoặc bệnh trong gia đình.",familyNote:"Bệnh di truyền trong gia đình",surgeryTitle:"Phẫu thuật / Nhập viện",surgeryDesc:"Phẫu thuật, nằm viện, gây mê và thủ thuật lớn.",surgeryExample:"Lịch sử phẫu thuật",medTitle:"Lịch sử dùng thuốc",medDesc:"Thuốc kê đơn, không kê đơn, thực phẩm bổ sung và phản ứng bất lợi.",medExample:"Tên thuốc",allergyTitle:"Dị ứng & Phản ứng bất lợi",allergyDesc:"Thông tin rất quan trọng khi cấp cứu hoặc khám ở nước ngoài.",drugAllergy:"Dị ứng thuốc",otherAllergy:"Dị ứng thực phẩm, môi trường hoặc khác",vaccineTitle:"Tiêm chủng",vaccineDesc:"Thuận tiện khi đi du lịch và khám bệnh.",labTitle:"Xét nghiệm quan trọng",labDesc:"Kết quả và ngày xét nghiệm cần theo dõi lâu dài.",lifestyleTitle:"Lối sống & Thói quen",lifestyleDesc:"Thông tin nền hữu ích cho nhân viên y tế.",vitalsTitle:"Chỉ số sức khỏe",vitalsDesc:"Giá trị cơ bản để so sánh khi khám.",specialTitle:"Thông tin y tế đặc biệt",specialDesc:"Bổ sung những thông tin quan trọng dễ bị bỏ sót.",documentsTitle:"Danh mục tài liệu y tế",documentsDesc:"Ghi lại báo cáo và hồ sơ; phiên bản chính thức có thể kết nối kho lưu trữ an toàn.",add:"＋ Thêm bản ghi",footer:"MyMed Passport · Demo frontend tĩnh · Không phải hệ thống chẩn đoán hoặc hồ sơ y tế chính thức"}
};

function applyLanguage(lang){
  document.documentElement.lang=lang;
  document.querySelectorAll("[data-i18n]").forEach(el=>{
    const key=el.dataset.i18n;if(translations[lang][key])el.innerHTML=translations[lang][key];
  });
}
document.getElementById("language").addEventListener("change",e=>applyLanguage(e.target.value));
function scrollToForm(){document.getElementById("form").scrollIntoView({behavior:"smooth"})}
function toast(msg){const t=document.getElementById("toast");t.textContent=msg;t.classList.add("show");setTimeout(()=>t.classList.remove("show"),2200)}
function addRow(btn){
  const row=document.createElement("div");row.className="row";
  row.innerHTML='<div><strong>New record</strong><span> — click to edit details</span></div><button onclick="removeRow(this)">×</button>';
  btn.parentElement.insertBefore(row,btn); updateCounts();
}
function removeRow(btn){btn.parentElement.remove();updateCounts()}
function updateCounts(){
  document.getElementById("medPreview").textContent=document.querySelectorAll(".section-card:nth-child(5) .row").length;
  document.getElementById("surgeryPreview").textContent=document.querySelectorAll(".section-card:nth-child(4) .row").length;
}
function exportData(){
  const data={name:document.getElementById("name").value,bloodType:document.getElementById("blood").value,exportedAt:new Date().toISOString()};
  const blob=new Blob([JSON.stringify(data,null,2)],{type:"application/json"});
  const a=document.createElement("a");a.href=URL.createObjectURL(blob);a.download="mymed-passport.json";a.click();
  toast(document.getElementById("language").value==="zh"?"已匯出 JSON 健康資料":"Health data exported as JSON");
}
document.getElementById("name").addEventListener("input",e=>document.getElementById("previewName").textContent=e.target.value||"Your Name");
document.getElementById("blood").addEventListener("change",e=>document.getElementById("bloodPreview").textContent=e.target.value||"—");
document.getElementById("language").value="zh";applyLanguage("zh");updateCounts();
</script>
</body>
</html>
