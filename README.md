
<html>
<head>
	<title>Midterm 2 preparation</title>
	<script type="text/javascript">
		function validateForm(){
			//checking the name
			var name = document.getElementById("name");
			if (name.value == ""){
				alert("Please enter your name");
				name.focus();
				return false;
			} else {
				var regExpName = /^[A-Z][a-z]+\s[A-Z][a-z]+$/;
				if (!regExpName.test(name.value)){
					alert("Please enter name in correct format");
					name.focus();
					return false;
				} 
			}
			
			//check if the city was selected
			if (document.getElementById("city").value == "-1"){
				alert("You must provide your city");
				return false;
			}
			
			//check if zip is correct
			var zip = document.getElementById("zip");
			if(zip.value == ""){
				alert("Please enter your zip code");
				zip.focus();
				return false;
			} else {
				var regExpZip = /^[1-9][0-9]{4}$/;
				if(!regExpZip.test(zip.value)){
					alert("Zip code must be in range 10000-99999");
					zip.focus();
					return false;
				}
			}
			
			//check address
			var address = document.getElementById("address");
			if(address.value == ""){
				alert("Please enter your address");
				address.focus();
				return false;
			} else {
				var regExpAddress = /^[A-Z][a-z]+(\s[A-Z][a-z]+)*\s[0-9]{1,3}([a-z])?$/;
				if(!regExpAddress.test(address.value)){
					alert("Address is not in correct format");
					address.focus();
					return false;
				}
			}
			
			//check phone
			var phone = document.getElementById("phone");
			if(phone.value == ""){
				alert("Please enter your phone");
				phone.focus();
				return false;
			} else {
				//063-555-555 or 063-555-5550
				var regExpPhone = /^06[0-9]-[0-9]{3}-[0-9]{3,4}$/;
				if(!regExpPhone.test(phone.value)){
					alert("Phone is not in correct format");
					phone.focus();
					return false;
				}
			}
			
			//check email
			var email = document.getElementById("email");
			if(email.value == ""){
				alert("Please enter your email");
				email.focus();
				return false;
			} else {
				//validate email
				var regExpEmail = 	
/^(([^<>()\[\]\\.,;:\s@"]+(\.[^<>()\[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/;
				if(!regExpEmail.test(email.value)){
					alert("Email is not in correct format");
					email.focus();
					return false;
				}
			}
			
			//check if the shipment was selected
			if (document.getElementById("shipment").value == "-1"){
				alert("You must provide your shipment option");
				document.getElementById("shipment").focus();
				return false;
			}
			
			//check date
			var date = document.getElementById("date");
			if(date.value == ""){
				alert("Please enter date");
				date.focus();
				return false;
			} else {
				
				var regExpDate = /^(0?[1-9]|[12][0-9]|3[01])[\/\-](0?[1-9]|1[012])[\/\-]\d{4}$/;
				if(!regExpDate.test(date.value)){
					alert("Date is not in correct format");
					date.focus();
					return false;
				}
			}
			
			//check time, hh:mm, 24h format and 12h format HH:MMPM
			var time1 = document.getElementById("time1");
			if(time1.value == ""){
				alert("Please enter the time");
				time1.focus();
				return false;
			} else {
				//var regExpTime = /^(2[0-3]|[01]?[0-9]):([0-5]?[0-9])$/;
				var regExpTime = /^(1[0-2]|0?[1-9]):([0-5]?[0-9])([AP]M)$/;
				if (!regExpTime.test(time1.value)){
				alert("Please enter time in the correct format");
				time1.focus();
				return false;
				}
			}
			
			//check if the credit card was selected
			if (document.getElementById("creditcard").value == "-1"){
				alert("You must provide your credit card");
				return false;
			}
			
			//check if the credit card is in correct format 16 digits 4-4-4-4
			var cc = document.getElementById("cc");
			if(cc.value == ""){
				alert("Please enter the cc");
				cc.focus();
				return false;
			} else {
				
				var regExpCC = /^[0-9]{4}-[0-9]{4}-[0-9]{4}-[0-9]{4}$/;
				if (!regExpCC.test(cc.value)){
				alert("Please enter cc in the correct format");
				cc.focus();
				return false;
				}
			}
			
			
		}
		
	
	
	function checkCC(){
		if (document.getElementById("creditcard").value != "-1"){
				document.getElementById("cc").disabled = false;
			} else {
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
				<td>
					<select name="city" id="city">
						<option value="-1" selected>[choose your city]<option>
						<option value="1">Belgrade<option>
						<option value="2">Novi Sad<option>
						<option value="3">Nis<option>
						<option value="4">Subotica<option>
					</select>
				</td>
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
				<td>Shipment method</td>
				<td>
					<select name="shipment" id="shipment">
						<option value="-1" selected>[you must choose method]</option>
						<option value="1">Regular post</option>
						<option value="2">Express post</option>
						<option value="3">Courier service</option>
						<option value="4">Manual take over</option>
					</select>
				</td>
			</tr>
			<tr>
				<td>Preferred Date</td>
				<td><input type="text" id="date"></td>
			</tr>
			<tr>
				<td>Preferred Time</td>
				<td><input type="text" id="time1"></td>
			</tr>
			<tr>
				<td>Credit Card</td>
				<td>
				<select name="creditcard" id="creditcard" onChange="checkCC();">
						<option value="-1" selected>[which credit card]</option>
						<option value="1">Master</option>
						<option value="2">American Express</option>
						<option value="3">Visa</option>
						<option value="4">Paypal</option>
				</select>
				</td>
			</tr>
			<tr>
				<td>CC number</td>
				<td><input type="text" id="cc" disabled></td>
			</tr>
			<tr>
				<td>Submit data</td>
				<td><input type="submit" value="send order"></td>
			</tr>
			<tr>
				<td>Reset data</td>
				<td><input type="reset" value="reset data"></td>
			</tr>
		</table>
	</form>
</body>
</html>
