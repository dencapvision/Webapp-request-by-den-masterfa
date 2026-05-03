import { useState } from "react";

const STEPS = [
  { id: 1, label: "ตัวตน & แบรนด์", icon: "👤" },
  { id: 2, label: "สินค้า / บริการ", icon: "💼" },
  { id: 3, label: "กลุ่มเป้าหมาย", icon: "🎯" },
  { id: 4, label: "ปัญหา & ผลลัพธ์", icon: "✨" },
  { id: 5, label: "หลักฐาน & ความน่าเชื่อถือ", icon: "🏆" },
  { id: 6, label: "Offer & ราคา", icon: "💰" },
  { id: 7, label: "Visual & สไตล์", icon: "🎨" },
  { id: 8, label: "CTA & ติดต่อ", icon: "📞" },
];

const initialData = {
  // Step 1
  ownerName: "",
  brandName: "",
  tagline: "",
  ownerRole: "",
  experience: "",
  ownerStory: "",
  socialProfiles: "",
  // Step 2
  productName: "",
  productType: "",
  productDescription: "",
  format: [],
  duration: "",
  location: "",
  capacity: "",
  // Step 3
  targetGroup: "",
  targetAge: "",
  targetPain: "",
  targetDream: "",
  targetOccupation: "",
  // Step 4
  problemBefore: "",
  transformation: "",
  outcomes: "",
  uniqueMethod: "",
  whyYou: "",
  // Step 5
  testimonials: "",
  clientLogos: "",
  mediaFeatures: "",
  certifications: "",
  caseStudy: "",
  // Step 6
  priceMain: "",
  priceNote: "",
  bonuses: "",
  guarantee: "",
  urgency: "",
  paymentOptions: "",
  // Step 7
  colorPreference: "",
  toneStyle: "",
  fontFeel: "",
  referenceLinks: "",
  logoAvailable: "",
  photoAvailable: "",
  // Step 8
  ctaText: "",
  lineId: "",
  phone: "",
  email: "",
  formLink: "",
  deadline: "",
};

const colors = {
  navy: "#0D1B3E",
  teal: "#1A7A6E",
  gold: "#C9A84C",
  tealLight: "#22A699",
  navyLight: "#1a2f5a",
  cream: "#FDFAF4",
  goldLight: "#E8C96A",
};

const inputStyle = {
  width: "100%",
  padding: "12px 16px",
  borderRadius: "10px",
  border: `1.5px solid #dde3ef`,
  fontSize: "15px",
  fontFamily: "'Sarabun', sans-serif",
  color: colors.navy,
  background: "#fff",
  outline: "none",
  transition: "border-color 0.2s",
  boxSizing: "border-box",
};

const textareaStyle = {
  ...inputStyle,
  minHeight: "100px",
  resize: "vertical",
};

const labelStyle = {
  display: "block",
  fontWeight: "700",
  fontSize: "14px",
  color: colors.navy,
  marginBottom: "6px",
  fontFamily: "'Prompt', sans-serif",
};

const hintStyle = {
  fontSize: "12px",
  color: "#8a97b5",
  marginTop: "4px",
  fontFamily: "'Sarabun', sans-serif",
};

function Field({ label, hint, children }) {
  return (
    <div style={{ marginBottom: "22px" }}>
      <label style={labelStyle}>{label}</label>
      {children}
      {hint && <p style={hintStyle}>💡 {hint}</p>}
    </div>
  );
}

function Input({ value, onChange, placeholder, type = "text" }) {
  const [focused, setFocused] = useState(false);
  return (
    <input
      type={type}
      value={value}
      onChange={(e) => onChange(e.target.value)}
      placeholder={placeholder}
      style={{
        ...inputStyle,
        borderColor: focused ? colors.teal : "#dde3ef",
        boxShadow: focused ? `0 0 0 3px ${colors.teal}22` : "none",
      }}
      onFocus={() => setFocused(true)}
      onBlur={() => setFocused(false)}
    />
  );
}

function Textarea({ value, onChange, placeholder, rows = 4 }) {
  const [focused, setFocused] = useState(false);
  return (
    <textarea
      value={value}
      onChange={(e) => onChange(e.target.value)}
      placeholder={placeholder}
      rows={rows}
      style={{
        ...textareaStyle,
        borderColor: focused ? colors.teal : "#dde3ef",
        boxShadow: focused ? `0 0 0 3px ${colors.teal}22` : "none",
      }}
      onFocus={() => setFocused(false)}
      onBlur={() => setFocused(false)}
    />
  );
}

function CheckGroup({ options, selected, onChange }) {
  const toggle = (v) => {
    if (selected.includes(v)) onChange(selected.filter((x) => x !== v));
    else onChange([...selected, v]);
  };
  return (
    <div style={{ display: "flex", flexWrap: "wrap", gap: "10px" }}>
      {options.map((opt) => {
        const active = selected.includes(opt);
        return (
          <button
            key={opt}
            onClick={() => toggle(opt)}
            style={{
              padding: "8px 16px",
              borderRadius: "30px",
              border: `1.5px solid ${active ? colors.teal : "#ccd3e0"}`,
              background: active ? colors.teal : "#fff",
              color: active ? "#fff" : colors.navy,
              fontFamily: "'Sarabun', sans-serif",
              fontSize: "14px",
              cursor: "pointer",
              fontWeight: active ? "700" : "400",
              transition: "all 0.2s",
            }}
          >
            {opt}
          </button>
        );
      })}
    </div>
  );
}

// ============ STEP COMPONENTS ============

function Step1({ data, set }) {
  return (
    <>
      <SectionTitle>👤 ข้อมูลตัวตนและแบรนด์</SectionTitle>
      <Field label="ชื่อ-นามสกุล / ชื่อที่ใช้เรียก *" hint="ชื่อที่ลูกค้าจะเห็นบน Sale Page">
        <Input value={data.ownerName} onChange={(v) => set("ownerName", v)} placeholder="เช่น ครูเด่น มาสเตอร์ฟา / อาจารย์อนุสรณ์ หนองนา" />
      </Field>
      <Field label="ชื่อแบรนด์ / สถาบัน / บริษัท *">
        <Input value={data.brandName} onChange={(v) => set("brandName", v)} placeholder="เช่น CAP Vision Institute" />
      </Field>
      <Field label="Tagline หรือสโลแกนของแบรนด์" hint="ประโยคที่สะท้อนตัวตนแบรนด์ใน 1 บรรทัด">
        <Input value={data.tagline} onChange={(v) => set("tagline", v)} placeholder="เช่น Transform People, Transform Organization" />
      </Field>
      <Field label="ตำแหน่ง / บทบาทของคุณ *">
        <Input value={data.ownerRole} onChange={(v) => set("ownerRole", v)} placeholder="เช่น Master Facilitator, ที่ปรึกษาทางการเงิน, นักโภชนาการ" />
      </Field>
      <Field label="ประสบการณ์ / ความเชี่ยวชาญ" hint="กี่ปี / กี่เวที / กี่องค์กร / วุฒิการศึกษา / ประกาศนียบัตร">
        <Textarea value={data.experience} onChange={(v) => set("experience", v)} placeholder="เช่น ประสบการณ์ 18+ ปี, 1,000+ เวที, 100+ องค์กร, วท.บ. ฟิสิกส์ มศว" />
      </Field>
      <Field label="เรื่องราวของคุณ (Origin Story)" hint="เส้นทางชีวิต จุดเปลี่ยน หรือเหตุผลที่ทำงานนี้ — ช่วยสร้างความเชื่อมั่น">
        <Textarea value={data.ownerStory} onChange={(v) => set("ownerStory", v)} placeholder="เล่าสั้นๆ ว่าทำไมถึงทำงานนี้ มีจุดเปลี่ยนอะไร..." rows={5} />
      </Field>
      <Field label="Social Media / ช่องทางออนไลน์">
        <Textarea value={data.socialProfiles} onChange={(v) => set("socialProfiles", v)} placeholder="LINE ID: @denmasterfa&#10;TikTok: @denmasterfa&#10;Facebook: @cheumkon&#10;Website: capvisionpartner.com" rows={4} />
      </Field>
    </>
  );
}

function Step2({ data, set }) {
  return (
    <>
      <SectionTitle>💼 ข้อมูลสินค้า / บริการ</SectionTitle>
      <Field label="ชื่อสินค้า / บริการ / คอร์ส *">
        <Input value={data.productName} onChange={(v) => set("productName", v)} placeholder="เช่น Team Talk Flow Workshop, คอร์สพูดอย่างไรให้ได้ใจ" />
      </Field>
      <Field label="ประเภทสินค้า / บริการ *">
        <Input value={data.productType} onChange={(v) => set("productType", v)} placeholder="เช่น Workshop, Online Course, Coaching 1:1, บริการรับเหมา, สินค้า" />
      </Field>
      <Field label="คำอธิบายสินค้า / บริการโดยย่อ *" hint="อธิบายให้คนที่ไม่รู้จักเข้าใจได้ใน 2-3 ประโยค">
        <Textarea value={data.productDescription} onChange={(v) => set("productDescription", v)} placeholder="บอกว่าคืออะไร ทำอะไร และได้อะไรจากมัน..." />
      </Field>
      <Field label="รูปแบบการให้บริการ">
        <CheckGroup
          options={["Onsite", "Online (Live)", "Online (Self-Paced)", "Hybrid", "1-on-1", "Group", "In-house", "Public"]}
          selected={data.format}
          onChange={(v) => set("format", v)}
        />
      </Field>
      <Field label="ระยะเวลา" hint="เช่น 1 วัน / 6 ชั่วโมง / 8 สัปดาห์">
        <Input value={data.duration} onChange={(v) => set("duration", v)} placeholder="เช่น 2 วัน (16 ชั่วโมง), 3 เดือน" />
      </Field>
      <Field label="สถานที่ / Platform">
        <Input value={data.location} onChange={(v) => set("location", v)} placeholder="เช่น โรงแรม / Zoom / Google Meet / บริษัทลูกค้า" />
      </Field>
      <Field label="จำนวนผู้เข้าร่วม (สูงสุด)">
        <Input value={data.capacity} onChange={(v) => set("capacity", v)} placeholder="เช่น 20-30 คน / ไม่จำกัด" />
      </Field>
    </>
  );
}

function Step3({ data, set }) {
  return (
    <>
      <SectionTitle>🎯 กลุ่มเป้าหมาย</SectionTitle>
      <Field label="กลุ่มเป้าหมายหลัก *" hint="ระบุให้ชัดเจนที่สุด ยิ่งเจาะจงยิ่งดี">
        <Textarea value={data.targetGroup} onChange={(v) => set("targetGroup", v)} placeholder="เช่น HR Manager และ Training Manager ในองค์กรขนาดกลาง-ใหญ่ ที่ต้องการพัฒนาทักษะทีม" />
      </Field>
      <Field label="อาชีพ / ตำแหน่ง / อุตสาหกรรม">
        <Input value={data.targetOccupation} onChange={(v) => set("targetOccupation", v)} placeholder="เช่น ผู้จัดการ, เจ้าของธุรกิจ, แม่บ้าน, นักศึกษาจบใหม่" />
      </Field>
      <Field label="ช่วงอายุโดยประมาณ">
        <Input value={data.targetAge} onChange={(v) => set("targetAge", v)} placeholder="เช่น 28-45 ปี" />
      </Field>
      <Field label="Pain Point — ปัญหา / ความเจ็บปวดที่กลุ่มเป้าหมายเผชิญ *" hint="เขียนให้เหมือนพูดแทนเขา ให้เขาอ่านแล้วรู้สึกว่า 'นี่แหละคือฉัน'">
        <Textarea value={data.targetPain} onChange={(v) => set("targetPain", v)} placeholder="เช่น ทีมสื่อสารกันไม่รู้เรื่อง / รู้สึกว่าตัวเองพูดไม่เก่ง / งานล้นแต่ไม่รู้จะจัดการอย่างไร..." rows={5} />
      </Field>
      <Field label="ความฝัน / สิ่งที่อยากได้ *" hint="พวกเขาอยากได้ผลลัพธ์อะไรจริงๆ">
        <Textarea value={data.targetDream} onChange={(v) => set("targetDream", v)} placeholder="เช่น อยากให้ทีมทำงานร่วมกันได้อย่างราบรื่น / อยากมีความมั่นใจในการพูด..." rows={4} />
      </Field>
    </>
  );
}

function Step4({ data, set }) {
  return (
    <>
      <SectionTitle>✨ ปัญหาที่แก้ & การเปลี่ยนแปลง</SectionTitle>
      <Field label="ชีวิตก่อนใช้บริการ (Before) *" hint="อธิบายสภาพปัญหาที่ลูกค้ากำลังเจออยู่">
        <Textarea value={data.problemBefore} onChange={(v) => set("problemBefore", v)} placeholder="เช่น ก่อนมาเรียน ผู้เรียนมักรู้สึกว่าการประชุมไม่มีประสิทธิภาพ ทีมต่างฝ่ายต่างทำ ไม่มีใครรับฟังกันจริงๆ..." rows={4} />
      </Field>
      <Field label="การเปลี่ยนแปลง (Transformation) *" hint="บอกว่าสินค้า/บริการทำให้เกิดอะไรขึ้น">
        <Textarea value={data.transformation} onChange={(v) => set("transformation", v)} placeholder="เช่น หลังจบ Workshop ทีมเริ่มฟังกันมากขึ้น ประชุมสั้นลงแต่ได้ผลลัพธ์มากขึ้น..." rows={4} />
      </Field>
      <Field label="ผลลัพธ์ที่วัดได้ (Outcomes) *" hint="ยิ่งมีตัวเลขยิ่งดี">
        <Textarea value={data.outcomes} onChange={(v) => set("outcomes", v)} placeholder="เช่น ยอดขายเพิ่ม 23% / ความพึงพอใจทีม 4.8/5 / ลดเวลาประชุมลง 40%..." rows={4} />
      </Field>
      <Field label="วิธีการ / Methodology ที่ใช้" hint="อธิบายกระบวนการทำงานของคุณ ทำให้ดูมืออาชีพ">
        <Textarea value={data.uniqueMethod} onChange={(v) => set("uniqueMethod", v)} placeholder="เช่น ใช้กระบวนการ CAP Theory: Cognition → Affection → Practice / Flow Learning 5 ขั้นตอน..." rows={4} />
      </Field>
      <Field label="ทำไมต้องเลือกคุณ? (Why You)" hint="จุดแตกต่างที่คนอื่นทำไม่ได้">
        <Textarea value={data.whyYou} onChange={(v) => set("whyYou", v)} placeholder="เช่น เป็นคนเดียวที่ใช้ Brainwave Tracker ในการฝึกอบรม / ประสบการณ์โดยตรงจากองค์กรระดับโลก..." rows={4} />
      </Field>
    </>
  );
}

function Step5({ data, set }) {
  return (
    <>
      <SectionTitle>🏆 หลักฐานและความน่าเชื่อถือ</SectionTitle>
      <Field label="Testimonials / รีวิวจากลูกค้า *" hint="คัดที่ดีที่สุด 3-5 ข้อ พร้อมชื่อและตำแหน่ง">
        <Textarea value={data.testimonials} onChange={(v) => set("testimonials", v)} placeholder={'เช่น "หลังเข้า Workshop ทีมเราสื่อสารกันดีขึ้นมาก..." — คุณสมศรี ผู้จัดการฝ่าย HR บริษัท XYZ\n\n"ครูเด่นสอนได้เข้าใจง่ายมาก นำไปใช้ได้ทันที..." — อาจารย์วิชัย มหาวิทยาลัย ABC'} rows={8} />
      </Field>
      <Field label="ลูกค้า / องค์กรที่เคยร่วมงาน" hint="ชื่อองค์กรหรือแบรนด์ที่มีชื่อเสียง จะช่วยเพิ่มความน่าเชื่อถือมาก">
        <Textarea value={data.clientLogos} onChange={(v) => set("clientLogos", v)} placeholder="เช่น Toyota Motor Thailand, Dell Technologies, กรมสรรพากร, ไทยประกันชีวิต..." rows={4} />
      </Field>
      <Field label="การปรากฏตัวในสื่อ / Media Features">
        <Textarea value={data.mediaFeatures} onChange={(v) => set("mediaFeatures", v)} placeholder="เช่น ถูกสัมภาษณ์ใน Manager Online / พูดบนเวที TEDx / รายการ TV / Podcast..." rows={3} />
      </Field>
      <Field label="ประกาศนียบัตร / รางวัล / การรับรอง">
        <Textarea value={data.certifications} onChange={(v) => set("certifications", v)} placeholder="เช่น Certified Facilitator จาก IAF / รางวัลวิทยากรดีเด่น..." rows={3} />
      </Field>
      <Field label="Case Study ที่โดดเด่น" hint="เล่าเรื่อง 1 เคสที่ประสบความสำเร็จชัดเจน">
        <Textarea value={data.caseStudy} onChange={(v) => set("caseStudy", v)} placeholder="องค์กร: (ประเภท) / ปัญหา: / กระบวนการที่ใช้: / ผลลัพธ์: ..." rows={5} />
      </Field>
    </>
  );
}

function Step6({ data, set }) {
  return (
    <>
      <SectionTitle>💰 Offer & ราคา</SectionTitle>
      <Field label="ราคาหลัก / Package หลัก *">
        <Input value={data.priceMain} onChange={(v) => set("priceMain", v)} placeholder="เช่น 15,000 บาท/คน / เริ่มต้น 120,000 บาท (In-house)" />
      </Field>
      <Field label="หมายเหตุเรื่องราคา / Package อื่น" hint="มี Tier อื่นไหม? ราคา Early Bird? ราคากลุ่ม?">
        <Textarea value={data.priceNote} onChange={(v) => set("priceNote", v)} placeholder="เช่น Early Bird ลด 20% / สมัชิก VIP ราคาพิเศษ / กลุ่ม 3+ คน ลด 15%..." rows={4} />
      </Field>
      <Field label="Bonus / ของแถม / สิ่งที่ได้รับเพิ่ม" hint="ยิ่งดูคุ้มค่ายิ่งดี">
        <Textarea value={data.bonuses} onChange={(v) => set("bonuses", v)} placeholder="เช่น ✅ Workbook มูลค่า 300 บาท&#10;✅ Recording 30 วัน&#10;✅ Group LINE ติดตามผล 3 เดือน..." rows={5} />
      </Field>
      <Field label="การรับประกัน / Guarantee" hint="ช่วยลดความกังวลของผู้ซื้อ">
        <Textarea value={data.guarantee} onChange={(v) => set("guarantee", v)} placeholder="เช่น รับประกันความพึงพอใจ 100% หากไม่ได้ผลภายใน 7 วัน ยินดีคืนเงิน..." rows={3} />
      </Field>
      <Field label="ความเร่งด่วน / Urgency / Scarcity" hint="ทำให้คนตัดสินใจเร็วขึ้น">
        <Textarea value={data.urgency} onChange={(v) => set("urgency", v)} placeholder="เช่น เปิดรับเพียง 20 คนเท่านั้น / รุ่นนี้ปิดรับ 31 พ.ค. นี้..." rows={3} />
      </Field>
      <Field label="ช่องทางชำระเงิน">
        <Input value={data.paymentOptions} onChange={(v) => set("paymentOptions", v)} placeholder="เช่น โอนธนาคาร, บัตรเครดิต, ผ่อน 0% 3 เดือน" />
      </Field>
    </>
  );
}

function Step7({ data, set }) {
  return (
    <>
      <SectionTitle>🎨 Visual & สไตล์การออกแบบ</SectionTitle>
      <Field label="สีหลักที่ชอบหรือใช้อยู่" hint="ใส่ชื่อสี / Hex Code / หรืออธิบายความรู้สึก">
        <Input value={data.colorPreference} onChange={(v) => set("colorPreference", v)} placeholder="เช่น Navy #0D1B3E + Teal #1A7A6E + Gold #C9A84C / สีเขียวหยก, ทอง" />
      </Field>
      <Field label="Tone & Style ที่ต้องการ">
        <CheckGroup
          options={["Professional", "Warm & Friendly", "Bold & Energetic", "Luxury", "Minimalist", "Playful", "Nature", "Dark & Premium"]}
          selected={data.toneStyle ? data.toneStyle.split(",") : []}
          onChange={(v) => set("toneStyle", v.join(","))}
        />
      </Field>
      <Field label="ความรู้สึกของ Font / ตัวอักษร">
        <Input value={data.fontFeel} onChange={(v) => set("fontFeel", v)} placeholder="เช่น ดูน่าเชื่อถือ / อ่านง่าย / ทันสมัย / อบอุ่น / หรู" />
      </Field>
      <Field label="Sale Page อ้างอิง (ที่ชอบ)" hint="ลิงก์ Sale Page ที่ดูแล้วรู้สึกชอบ เพื่อใช้เป็น Reference">
        <Textarea value={data.referenceLinks} onChange={(v) => set("referenceLinks", v)} placeholder="วางลิงก์ได้เลย เช่น&#10;https://watsayamon-sake-page.vercel.app/&#10;https://..." rows={3} />
      </Field>
      <Field label="มี Logo / Branding ที่ใช้อยู่แล้วไหม?">
        <CheckGroup
          options={["มี Logo พร้อมใช้", "มีแต่ต้องปรับ", "ยังไม่มี (ต้องสร้างใหม่)"]}
          selected={data.logoAvailable ? [data.logoAvailable] : []}
          onChange={(v) => set("logoAvailable", v[v.length - 1] || "")}
        />
      </Field>
      <Field label="มีรูปโปรไฟล์ / รูปสินค้า / รูปอบรมไหม?">
        <CheckGroup
          options={["มีรูปคุณภาพดีพร้อมใช้", "มีบ้าง", "ยังไม่มี ต้องถ่ายใหม่"]}
          selected={data.photoAvailable ? [data.photoAvailable] : []}
          onChange={(v) => set("photoAvailable", v[v.length - 1] || "")}
        />
      </Field>
    </>
  );
}

function Step8({ data, set }) {
  return (
    <>
      <SectionTitle>📞 CTA & ข้อมูลการติดต่อ</SectionTitle>
      <Field label="ข้อความ Call-to-Action (ปุ่มหลัก) *" hint="ประโยคที่ให้คนกดสมัคร/ติดต่อ">
        <Input value={data.ctaText} onChange={(v) => set("ctaText", v)} placeholder="เช่น สมัครเลย / จองที่นั่ง / ขอใบเสนอราคา / ปรึกษาฟรี" />
      </Field>
      <Field label="LINE ID / LINE OA">
        <Input value={data.lineId} onChange={(v) => set("lineId", v)} placeholder="เช่น @denmasterfa" />
      </Field>
      <Field label="เบอร์โทรศัพท์">
        <Input value={data.phone} onChange={(v) => set("phone", v)} placeholder="เช่น 093-223-5919" type="tel" />
      </Field>
      <Field label="Email">
        <Input value={data.email} onChange={(v) => set("email", v)} placeholder="เช่น dencapvision@gmail.com" type="email" />
      </Field>
      <Field label="ลิงก์ Form สมัคร / ลิงก์ชำระเงิน (ถ้ามี)">
        <Input value={data.formLink} onChange={(v) => set("formLink", v)} placeholder="เช่น https://forms.gle/..." />
      </Field>
      <Field label="Deadline / วันปิดรับสมัคร">
        <Input value={data.deadline} onChange={(v) => set("deadline", v)} placeholder="เช่น 31 พฤษภาคม 2567 / ไม่กำหนด" />
      </Field>
    </>
  );
}

function SectionTitle({ children }) {
  return (
    <div style={{ marginBottom: "24px" }}>
      <h2 style={{
        fontSize: "20px",
        fontWeight: "800",
        color: colors.navy,
        fontFamily: "'Prompt', sans-serif",
        margin: "0 0 4px",
      }}>{children}</h2>
      <div style={{ width: "48px", height: "3px", borderRadius: "4px", background: `linear-gradient(90deg, ${colors.teal}, ${colors.gold})` }} />
    </div>
  );
}

function Summary({ data }) {
  const sections = [
    { title: "👤 ตัวตน & แบรนด์", fields: [
      ["ชื่อ", data.ownerName], ["แบรนด์", data.brandName], ["Tagline", data.tagline],
      ["ตำแหน่ง", data.ownerRole], ["ประสบการณ์", data.experience],
      ["เรื่องราว", data.ownerStory], ["Social", data.socialProfiles],
    ]},
    { title: "💼 สินค้า / บริการ", fields: [
      ["ชื่อ", data.productName], ["ประเภท", data.productType],
      ["คำอธิบาย", data.productDescription], ["รูปแบบ", data.format.join(", ")],
      ["ระยะเวลา", data.duration], ["สถานที่", data.location], ["จำนวน", data.capacity],
    ]},
    { title: "🎯 กลุ่มเป้าหมาย", fields: [
      ["กลุ่มหลัก", data.targetGroup], ["อาชีพ", data.targetOccupation],
      ["อายุ", data.targetAge], ["Pain", data.targetPain], ["ความฝัน", data.targetDream],
    ]},
    { title: "✨ ปัญหา & ผลลัพธ์", fields: [
      ["Before", data.problemBefore], ["Transformation", data.transformation],
      ["Outcomes", data.outcomes], ["Methodology", data.uniqueMethod], ["Why You", data.whyYou],
    ]},
    { title: "🏆 หลักฐาน", fields: [
      ["Testimonials", data.testimonials], ["ลูกค้า", data.clientLogos],
      ["สื่อ", data.mediaFeatures], ["ประกาศนียบัตร", data.certifications], ["Case Study", data.caseStudy],
    ]},
    { title: "💰 Offer & ราคา", fields: [
      ["ราคาหลัก", data.priceMain], ["Package/หมายเหตุ", data.priceNote],
      ["Bonus", data.bonuses], ["Guarantee", data.guarantee],
      ["Urgency", data.urgency], ["ชำระเงิน", data.paymentOptions],
    ]},
    { title: "🎨 Visual", fields: [
      ["สี", data.colorPreference], ["Tone", data.toneStyle], ["Font", data.fontFeel],
      ["Reference", data.referenceLinks], ["Logo", data.logoAvailable], ["รูปภาพ", data.photoAvailable],
    ]},
    { title: "📞 CTA & ติดต่อ", fields: [
      ["CTA", data.ctaText], ["LINE", data.lineId], ["โทร", data.phone],
      ["Email", data.email], ["Form Link", data.formLink], ["Deadline", data.deadline],
    ]},
  ];

  return (
    <div>
      <div style={{ textAlign: "center", marginBottom: "32px" }}>
        <div style={{ fontSize: "48px", marginBottom: "12px" }}>🎉</div>
        <h2 style={{ fontFamily: "'Prompt', sans-serif", color: colors.navy, fontSize: "22px", margin: "0 0 8px" }}>
          ข้อมูลครบแล้ว! พร้อมส่งให้ทีมแล้ว
        </h2>
        <p style={{ fontFamily: "'Sarabun', sans-serif", color: "#6b7a99", fontSize: "15px" }}>
          ด้านล่างคือสรุปข้อมูลทั้งหมดของคุณ — คัดลอกหรือ Download เพื่อส่งต่อได้เลย
        </p>
      </div>
      {sections.map((s) => (
        <div key={s.title} style={{ marginBottom: "24px", background: "#f8f9fc", borderRadius: "12px", padding: "20px", border: `1px solid #e8ecf4` }}>
          <h3 style={{ fontFamily: "'Prompt', sans-serif", color: colors.teal, fontSize: "16px", margin: "0 0 12px", fontWeight: "700" }}>{s.title}</h3>
          {s.fields.filter(([, v]) => v).map(([k, v]) => (
            <div key={k} style={{ display: "grid", gridTemplateColumns: "120px 1fr", gap: "8px", marginBottom: "8px" }}>
              <span style={{ fontFamily: "'Sarabun', sans-serif", fontSize: "13px", color: "#8a97b5", fontWeight: "700" }}>{k}</span>
              <span style={{ fontFamily: "'Sarabun', sans-serif", fontSize: "14px", color: colors.navy, whiteSpace: "pre-wrap" }}>{v}</span>
            </div>
          ))}
        </div>
      ))}
    </div>
  );
}

export default function App() {
  const [step, setStep] = useState(1);
  const [data, setData] = useState(initialData);
  const [submitted, setSubmitted] = useState(false);

  const set = (key, val) => setData((d) => ({ ...d, [key]: val }));

  const stepComponents = [Step1, Step2, Step3, Step4, Step5, Step6, Step7, Step8];
  const CurrentStep = stepComponents[step - 1];
  const progress = (step / STEPS.length) * 100;

  const handleSubmit = () => setSubmitted(true);

  return (
    <div style={{ minHeight: "100vh", background: colors.cream, fontFamily: "'Sarabun', sans-serif" }}>
      <link href="https://fonts.googleapis.com/css2?family=Prompt:wght@400;700;800;900&family=Sarabun:wght@400;600;700&display=swap" rel="stylesheet" />

      {/* Header */}
      <div style={{
        background: `linear-gradient(135deg, ${colors.navy} 0%, ${colors.navyLight} 60%, ${colors.teal} 100%)`,
        padding: "32px 24px 48px",
        textAlign: "center",
        position: "relative",
        overflow: "hidden",
      }}>
        <div style={{ position: "absolute", top: "-40px", right: "-40px", width: "160px", height: "160px", borderRadius: "50%", background: `${colors.gold}15` }} />
        <div style={{ position: "absolute", bottom: "-30px", left: "-30px", width: "120px", height: "120px", borderRadius: "50%", background: `${colors.teal}20` }} />
        <div style={{ position: "relative" }}>
          <div style={{ display: "inline-block", background: `${colors.gold}22`, border: `1px solid ${colors.gold}44`, borderRadius: "30px", padding: "6px 16px", marginBottom: "12px" }}>
            <span style={{ color: colors.goldLight, fontSize: "12px", fontWeight: "700", fontFamily: "'Prompt', sans-serif", letterSpacing: "1px" }}>
              CAP VISION INSTITUTE
            </span>
          </div>
          <h1 style={{ color: "#fff", fontSize: "26px", fontWeight: "900", fontFamily: "'Prompt', sans-serif", margin: "0 0 8px", lineHeight: 1.3 }}>
            📋 แบบฟอร์มข้อมูล
          </h1>
          <h2 style={{ color: colors.goldLight, fontSize: "18px", fontWeight: "700", fontFamily: "'Prompt', sans-serif", margin: "0 0 12px" }}>
            สำหรับสร้าง Sale Page
          </h2>
          <p style={{ color: "#9db4d0", fontSize: "14px", maxWidth: "400px", margin: "0 auto", lineHeight: 1.6 }}>
            กรอกข้อมูลให้ครบถ้วน เพื่อให้ทีมครูเด่น สร้าง Sale Page ที่ตรงใจและได้ผลสูงสุด
          </p>
        </div>
      </div>

      {/* Progress Bar */}
      {!submitted && (
        <div style={{ background: "#fff", borderBottom: "1px solid #eaecf4", padding: "0 16px" }}>
          <div style={{ maxWidth: "640px", margin: "0 auto", paddingTop: "16px" }}>
            {/* Step indicators */}
            <div style={{ display: "flex", justifyContent: "space-between", marginBottom: "8px", overflowX: "auto", gap: "4px" }}>
              {STEPS.map((s) => (
                <button
                  key={s.id}
                  onClick={() => setStep(s.id)}
                  style={{
                    display: "flex",
                    flexDirection: "column",
                    alignItems: "center",
                    gap: "2px",
                    background: "none",
                    border: "none",
                    cursor: "pointer",
                    padding: "4px 6px",
                    borderRadius: "8px",
                    minWidth: "60px",
                    opacity: s.id > step ? 0.4 : 1,
                  }}
                >
                  <span style={{ fontSize: "16px" }}>{s.icon}</span>
                  <span style={{
                    fontSize: "10px",
                    fontFamily: "'Sarabun', sans-serif",
                    color: s.id === step ? colors.teal : colors.navy,
                    fontWeight: s.id === step ? "700" : "400",
                    whiteSpace: "nowrap",
                  }}>{s.id === step ? s.label : s.id}</span>
                </button>
              ))}
            </div>
            {/* Progress */}
            <div style={{ height: "4px", background: "#e8ecf4", borderRadius: "4px", marginBottom: "4px" }}>
              <div style={{ height: "100%", width: `${progress}%`, borderRadius: "4px", background: `linear-gradient(90deg, ${colors.teal}, ${colors.gold})`, transition: "width 0.4s ease" }} />
            </div>
            <p style={{ fontSize: "12px", color: "#8a97b5", textAlign: "right", margin: "0 0 8px", fontFamily: "'Sarabun', sans-serif" }}>
              ขั้นตอน {step} / {STEPS.length}
            </p>
          </div>
        </div>
      )}

      {/* Main Content */}
      <div style={{ maxWidth: "640px", margin: "0 auto", padding: "24px 16px 80px" }}>
        {submitted ? (
          <Summary data={data} />
        ) : (
          <div style={{ background: "#fff", borderRadius: "16px", padding: "28px 24px", boxShadow: "0 4px 24px rgba(13,27,62,0.08)" }}>
            <CurrentStep data={data} set={set} />

            {/* Navigation */}
            <div style={{ display: "flex", justifyContent: "space-between", marginTop: "32px", gap: "12px" }}>
              {step > 1 && (
                <button
                  onClick={() => setStep(step - 1)}
                  style={{
                    flex: 1, padding: "14px", borderRadius: "10px",
                    border: `1.5px solid ${colors.navy}`, background: "transparent",
                    color: colors.navy, fontFamily: "'Prompt', sans-serif", fontWeight: "700",
                    fontSize: "15px", cursor: "pointer",
                  }}
                >
                  ← ย้อนกลับ
                </button>
              )}
              {step < STEPS.length ? (
                <button
                  onClick={() => setStep(step + 1)}
                  style={{
                    flex: 2, padding: "14px", borderRadius: "10px",
                    border: "none",
                    background: `linear-gradient(135deg, ${colors.teal}, ${colors.navy})`,
                    color: "#fff", fontFamily: "'Prompt', sans-serif", fontWeight: "700",
                    fontSize: "15px", cursor: "pointer",
                    boxShadow: `0 4px 16px ${colors.teal}44`,
                  }}
                >
                  ถัดไป →
                </button>
              ) : (
                <button
                  onClick={handleSubmit}
                  style={{
                    flex: 2, padding: "14px", borderRadius: "10px",
                    border: "none",
                    background: `linear-gradient(135deg, ${colors.gold}, #b8860b)`,
                    color: "#fff", fontFamily: "'Prompt', sans-serif", fontWeight: "800",
                    fontSize: "16px", cursor: "pointer",
                    boxShadow: `0 4px 16px ${colors.gold}66`,
                  }}
                >
                  🚀 ส่งข้อมูลเลย!
                </button>
              )}
            </div>
          </div>
        )}
      </div>

      {/* Footer */}
      <div style={{ textAlign: "center", padding: "16px", background: colors.navy }}>
        <p style={{ color: "#9db4d0", fontSize: "12px", fontFamily: "'Sarabun', sans-serif", margin: 0 }}>
          🌿 CAP Vision Institute · ครูเด่น มาสเตอร์ฟา · capvisionpartner.com
        </p>
      </div>
    </div>
  );
}
