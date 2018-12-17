# JS

<!DOCTYPE html>
<html>
<head>
	<meta charset="utf-8">
	<title></title>
	<script>
		function validateForm() {
			//check name
			var name = document.getElementById("name");
			if (name == "") {
				alert("Please enter you name!");
				name.focus();
				return false;
		} else {
			//name is not empty we must validate
			var regExpName = /^[A-Z][a-z]+\s[A-Z][a-z]+$/;
			if (!regExpName.test(name.value)) {
				alert("Please enter your name in correct form!");
				name.focus();
				return false;
			}
		}
		//check city
		if (document.getElementById("city").value == -1) {
			alert("Please provide your city!");
			return false;
		}
		//check zip, 10000-99999
		var zip = document.getElementById("zip");
	if (zip.value == "") {
		alert("You must provide your zip!");
		zip.focus();
		return false;
	} else {
		//zip is not empty we must validate
		var regExpZip = /^[1-9][0-9]{4}$/;
		if (!regExpZip.test(zip.value)) {
			alert("Zip is not in correct format!");
			zip.focus();
			return false;
		} 
	}
	//check address
	var address = document.getElementById("address");
	if (address == "") {
		alert("You must provide address!");
		address.focus();
		return false;
	} else {
		//address is not empty we must validate
		var regExpAddress = /^[A-Z][a-z]+(\s[A-Z][a-z]+)*\s[0-9]{1,3}([a-z])?$/;
		if (!regExpAddress.test(address.value)) {
			alert("Address is not in correct format!");
			address.focus();
			return false;
		}
	}
	//check phone
	var phone = document.getElementById("phone");
	if (phone.value == "") {
		alert("Please enter your phone");
		phone.focus();
		return false;
	} else {
		//user enter phone we must check validation
		//063-555-555 or 063-555-5550
		var regExpPhone = /^06[0-9]-[0-9]{3}-[0-9]{3,4}$/;
		if (!regExpPhone.test(phone.value)) {
			alert("Phone is not in correct format!");
			phone.focus();
			return false;
		}
	}
	//checking mail


	//check the shipment method
	if (document.getElementById("shipment").value == -1) {
		alert("You must select shipment method!");
		document.getElementById("shipment").focus();
		return false;
	}
	//check date
	var date = document.getElementById("date");
	if (date.value == "") {
		alert("You must enter delivery date!");
		date.focus();
		return false;
	} else {
		//user entered date we must validate dd-mm-yyyy, dd/mm/yyyy
		var regExpDate = /^(0?[1-9]|[12][0-9]|3[01])[\/\-](0?[1-9]|1[012])[\/\-]\d{4}$/;
		if (!regExpDate.test(date.value)) {
			alert("Date must be in format dd-mm-yyyy or dd/mm/yyyy");
			date.focus();
			return false;
		}
	}
	// check time hh:mm h:mm, 24h format, 12h HH:MMPM
	var time = document.getElementById("time");
	if (time.value == "") {
		alert("You must enter delevery time!");
		time.focus();
		return false;
	} else {
		//user entered time we must validate
		var regExpTime = /^(2[0-3]|[01]?[0-9]):([0-5][0-9])||((1[0-2]|0?[1-9]):([0-5][0-9]([AP]M)))$/; //24h and 12h format
		if (!regExpTime.test(time.value)) {
			alert("Wrong time format!");
			time.focus();
			return false;
		}
	}
	//check creditcard selected
	if (document.getElementById("creditcard").value == -1) {
		alert("Please provide your creditcard!");
		return false;
	}
	//credit card, 4-4-4-4
	var time = document.getElementById("cc");
	if (cc.value == "") {
		alert("!");
		cc.focus();
		return false;
	} else {
		//user entered time we must validate
		var regExpCc = /^[0-9]{4}-[0-9]{4}-[0-9]{4}-[0-9]{4}-[0-9]{4}$/;
		if (!regExpCc.test(cc.value)) {
			alert("Wrong cc format!");
			cc.focus();
			return false;
		}
	}
}
function checkcc () {
	if (document.getElementById("creditcard").value != -1) {
		document.getElementById("cc").disabled = false;
	}else {
		document.getElementById("cc").disabled = true;
	}
}
	</script>
</head>
<body>
	<form name="form1" action="/action.php" method="POST" onsubmit="return validateForm()">
		<table cellspacing="2" cellpadding="2" border="1">
			<tr>
				<td>Name</td>
				<td><input type="text" id="name"></td>
			</tr>
			<tr>
				<td>City</td>
				<td><select name="city" id="city">
					<option value="-1" selected>[choose your city]</option>
					<option value="2">Beograd</option>
					<option value="3">Novi Sad</option>
					<option value="4">Nis</option>
				</select></td>
			</tr>
			<tr>
				<td>ZIP</td>
				<td><input type="text" id="zip"></td>
			</tr>
			<tr>
				<td>Address</td>
				<td><input type="text" id="address"></td>
			</tr>
			<tr>
				<td>Phone</td>
				<td><input type="text" id="phone"></td>
			</tr>
			<tr>
				<td>Email</td>
				<td><input type="text" id="email"></td>
			</tr>
			<tr>
				<td>Shipment</td>
				<td><select name="shipment" id="shipment">
					<option value="-1">[you must choose method]</option>
					<option value="2">Regular post</option>
					<option value="3">Express post</option>
					<option value="4">Courier service</option>
					<option value="5">Manual take over</option>
				</select></td>
			</tr>
			<tr>
				<td>Preffered date</td>
				<td><input type="text" id="date"></td>
			</tr>
			<tr>
				<td>Preffered time</td>
				<td><input type="text" id="time"></td>
			</tr>
			<tr>
				<td>Credit Card</td>
				<td><select name="creditcard" id="creditcard" onchange="checkcc()">
					<option value="-1">[which credit card]</option>
					<option value="2">Master</option>
					<option value="3">Visa</option>
					<option value="4">American express</option>
					<option value="5">PayPal</option>
				</select></td>
			</tr>
			<tr>
				<td>CC number</td>
				<td><input type="text" id="cc" disabled></td>
			</tr>
			<tr>
				<td>Submit Data</td>
				<td><input type="submit" id="submit" value="Send order"></td>
			</tr>
			<tr>
				<td>Reset Data</td>
				<td><input type="reset" id="reset" value="Reset Data"></td>
			</tr>
		</table>
	</form>
</body>
</html>
