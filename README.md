<form action="https://docs.google.com/forms/d/e/1FAIpQLSdPjTJXCzGmFFpnNbmqMXLEgu4fG9qRlMmm9R5vNTwFpCnKhQ/formResponse" target="hidden_iframe" method="post" onsubmit="return test(this.wcheck.value)">
<p><input name="entry.1596121047" placeholder="名前" value="名無し" required></p>
<p><input name="entry.1596121047" placeholder="メールアドレス" type="email"></p>
<p><textarea name="entry.1596121047" placeholder="コメント" rows="10" cols="40" maxlength="400" id="wcheck" required></textarea></p>
<input type="submit" id="submitbutton" value="送信">
</form>
<iframe onload='if(submitted){window.location="";}' id=hidden_iframe name=hidden_iframe style=display:none></iframe>

<script type="text/javascript">
var NGComments = ["死ね","バカ",".exe"]; // 簡易的なNGワードの設定
var regex = new RegExp(NGComments.join("|"));
function test(wcheck) {
	if (wcheck.match(regex) != null) {
		alert("ERROR: コメントにNGワードが含まれています");
		return false;
	}
	document.getElementById("submitbutton").disabled = true;
	textareas = document.getElementsByTagName('textarea');
	for(var i=0 ;i < textareas.length ;i ++ ){
		textareas[i].value = textareas[i].value.replace( /</g ,'&lt;' );
	}
	inputs = document.getElementsByTagName('input');
	for(var i=0 ;i < inputs.length ;i ++ ){
		inputs[i].value = inputs[i].value.replace( /</g ,'&lt;' );
	}
	return submitted=!0;
}
</script>
