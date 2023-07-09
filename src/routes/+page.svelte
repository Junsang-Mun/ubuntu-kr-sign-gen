<script>
	let name_kr = '';
	let name_en = '';
	let title = '';
	let phone = '';
	let email = '';
	let gpg = '';

	let sign = '';

function generator(name_kr, name_en, title, phone, email, gpg) {
	sign = `<div style="font-family: system-ui; line-height: 16px !important; font-size: 14px;"><br><table style="width: 100%; border-collapse: collapse;"><tbody><tr><td style="width: 100px; border: 0px; height: 87.4451px;"><img src="https://raw.githubusercontent.com/ubuntu-kr/logo-artworks/main/UbuntuKrCircleTag_w100.png" style="display: block; margin: 5px 0px; text-align: left; width: 74px;"></td><td style="border: 0px solid rgb(221, 221, 221); padding: 3px 4px 2px; height: 87.4451px; vertical-align: middle;"><strong id="nameOrg" style="font-size:13px;color:#000;letter-spacing:-1px;">${name_kr}</strong><span id="nameEng" style="font-size:11px;color:#000;">&nbsp;${name_en}</span><br><span id="department" style="font-size:11px;color:#000;">${title} of Ubuntu Korea Community</span><div id="contactInfo" style="color:#7d7d7d;margin-top:7px;"><span style="font-size:11px;line-height:14px;color:#999;"><span style="font-weight:bold; color:#616161;">Mobile</span> <span style="font-size:11px; color:#7d7d7d;">${phone}&nbsp;</span></span><br><span style="font-size:11px;color:#999;"><span style="font-weight:bold; color:#616161;">Email</span>&nbsp; <span style="font-size:11px; color:#999;"><a href="mailto:${email}" target="_blank">${email}</a></span></span><br><span style="font-size:11px;line-height:14px;color:#999;">${gpg}</span></div></td></tr></tbody></table></div>`;
}
</script>

<h1>이메일 서명 생성기</h1>

<input bind:value={name_kr} type="text" required="true" placeholder="이름"/>
<input bind:value={name_en} type="text" required="true" placeholder="영문 이름"/>
<input bind:value={title} type="text" required="true" placeholder="직책"/>
<input bind:value={phone} type="tel" required="true" placeholder="휴대폰 번호"/>
<input bind:value={email} type="email" required="true" placeholder="메일 주소"/>
<input bind:value={gpg} type="text" required="true" placeholder="gpg 키"/>
<input type="submit" value="생성" on:click={generator(name_kr, name_en, title, phone, email, gpg)}/>

<pre>{sign}</pre>
<br>
<h1>미리보기</h1>
<div id="preview">
	{@html sign}
</div>