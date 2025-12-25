<script>
async function main() {
  document.body.innerHTML = "<h3>กำลังโหลด LIFF…</h3>";

  await liff.init({ liffId: "2008740636-oTHcHAmb" });

  if (!liff.isInClient()) {
    document.body.innerHTML = "<h3>❌ กรุณาเปิดลิงก์นี้ผ่าน LINE</h3>";
    return;
  }

  await liff.shareTargetPicker([
    {
      type: "text",
      text: "ทดสอบแชร์สำเร็จ 🎉"
    }
  ]);

  liff.closeWindow();
}
main();
</script>
