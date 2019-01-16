
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






















<!doctype html>
<html>
<head>
	<script type="text/javascript">
		function validateForm()
		{
			var name = document.getElementById("name");
			if(name.value == "")
			{
				alert("Please enter your name.");
				name.focus();
				return false;
			}
			else
			{
				var regExpName = /^[A-Z][a-z]{2,}\s[A-Z][a-z]+([\s\-][A-Z][a-z]+)*$/;
				if(!regExpName.test(name.value))
				{
					alert("Please enter your name in the correct form. Example: Petar Petrovic.");
					name.focus();
					return false;
				}
			}
			var city = document.getElementById("city");
			if(city.value == "")
			{
				alert("Please enter a city");
				city.focus();
				return false;
			}
			else
			{
				var regExpCity = /^[A-Z][a-z]+(\s[A-Z][a-z]+)*$/;
				if(!regExpCity.test(city.value))
				{
					alert("Please enter a city in a valid form.");
					city.focus();
					return false;
				}
			}
			var zip = document.getElementById("zip");
			if(zip.value == "")
			{
				alert("Please enter your ZIP code.");
				zip.focus();
				return false;
			}
			else
			{
				var regExpZip = /^[1-7][0-9]{4}$/;
				if(!regExpZip.test(zip.value))
				{
					alert("Please enter zip code between 10000-79999.");
					zip.focus();
					return false;
				}
			}
			var address = document.getElementById("address");
			if(address.value == "")
			{
				alert("Please enter your address");
				address.focus();
				return false;
			}
			else
			{
				var regExpAddress = /^[A-Z][a-z]+(\s[A-Z][a-z]+)*\s[1-9][0-9]{0,2}[a-z]?$/;
				if(!regExpAddress.test(address.value))
				{
					alert("Please enter address in the correct form. Example: Milesavska 9a.");
					address.focus();
					return false;
				}
			}
			var birthdate = document.getElementById("birthdate");
			if(birthdate.value == "")
			{
				alert("Please enter your date of birth.");
				birthdate.focus();
				return false;
			}
			else
			{
				var regExpBirthdate = /^((19[0-9][0-9])|(20((0[0-9])|1[0-8])))[\/]((0[1-9])|(1[0-2]))[\/](([0-2][1-9])|(3[01]))$/;
				if(!regExpBirthdate.test(birthdate.value))
				{
					alert("Please enter the date of your flight in the correct yyyy/mm/dd format.");
					birthdate.focus();
					return false;
				}
			}
			var passnum = document.getElementById("passnum");
			if(passnum.value == "")
			{
				alert("Please enter your passport number");
				passnum.focus();
				return false;
			}
			else
			{
				var regExpPassnum = /^[0-9]{3}([A-Za-z0-9]){6}$/
				if(!regExpPassnum.test(passnum.value))
				{
					alert("Please enter your passport number in the correct form. Example: 000xxxxxx.");
					passnum.focus();
					return false;
				}
			}
			var flyingfrom = document.getElementById("flyingfrom");
			if(flyingfrom.value == "")
			{
				alert("Please enter where you are flying from.");
				flyingfrom.focus();
				return false;
			}
			else
			{
				var regExpFlyingfrom = /^[A-Z][a-z]+(\s[A-Z][a-z]+)*$/;
				if(!regExpFlyingfrom.test(flyingfrom.value))
				{
					alert("Please enter where you are flying from in the correct format.");
					flyingfrom.focus();
					return false;
				}
			}
			var destination = document.getElementById("destination");
			if(destination.value == "")
			{
				alert("Please enter where your destination.");
				destination.focus();
				return false;
			}
			else
			{
				var regExpDestination = /^[A-Z][a-z]+(\s[A-Z][a-z]+)*$/;
				if(!regExpDestination.test(destination.value))
				{
					alert("Please enter where your destination in the correct format.");
					destination.focus();
					return false;
				}
			}
			var flightdate = document.getElementById("flightdate");
			if(flightdate.value == "")
			{
				alert("Please enter the date of your flight.");
				flightdate.focus();
				return false;
			}
			else
			{
				var regExpFlightdate = /^20((1[89])|([2-9]{2}))[\/]((0[1-9])|(1[0-2]))[\/](([0-2][1-9])|(3[01]))$/;
				if(!regExpFlightdate.test(flightdate.value))
				{
					alert("Please enter the date of your flight in the correct yyyy/mm/dd form.");
					flightdate.focus();
					return false;
				}
			}
			if(document.getElementById("returnflight").checked)
			{
				if(document.getElementById("returnflightdate").value == "")
				{
					alert("Please enter the date of your return flight.");
					returnflightdate.focus();
					return false;
				}
				else
				{
				var regExpReturnflightdate = /^20((1[89])|([2-9]{2}))[\/]((0[1-9])|(1[12]))[\/](([0-2][1-9])|(3[01]))$/;
				if(!regExpReturnflightdate.test(document.getElementById("returnflightdate").value))
				{
					alert("Please enter the date of your return flight in the correct yyyy/mm/dd form.");
					returnflightdate.focus();
					return false;
				}
				}
			}
			if(document.getElementById("airline").value == "-1")
			{
				alert("Please select an airline company");
				airline.focus()
				return false;
			}
			if(document.getElementById("firstclass").checked && document.getElementById("lunchmenu").value == "-1")
			{
					alert("Please select a lunch menu option");
					lunchmenu.focus();
					return false;
			}
			if(document.getElementById("cctype").value == "-1")
			{
				alert("Please select a credit card type for payment.");
				cctype.focus();
				return false;
			}
			var ccnum = document.getElementById("ccnum");
			if(ccnum.value == "")
			{
				alert("Please enter your credit card number.");
				ccnum.focus();
				return false;
			}
			else
			{
				var regExpCCnum = /^[0-9]{4}[\s\-][0-9]{4}[\s\-][0-9]{4}[\s\-][0-9]{4}$/;
				if(!regExpCCnum.test(ccnum.value))
				{
					alert("Please enter your credit card number in the correct form.");
					ccnum.focus();
					return false;
				}
			}
			var ccseccode = document.getElementById("ccseccode");
			if(ccseccode.value == "")
			{
				alert("Please enter your credit card security ccode.");
				ccseccode.focus();
				return false;
			}
			else
			{
				var regExpCCseccode = /^[0-9]{3}$/;
				if(!regExpCCseccode.test(ccseccode.value))
				{
					alert("Please enter the 3-digit credit card security code");
					ccseccode.focus();
					return false;
				}
			}
			var ccexpdate = document.getElementById("ccexpdate");
			if(ccexpdate.value == "")
			{
				alert("Please enter your credit card's expiry date.");
				ccexpdate.focus();
				return false;
			}
			else
			{
				var regExpCCexpdate = /^((0[1-9])|(1[0-2]))[\/]((1[89])|([2-9][0-9]))$/;
				if(!regExpCCexpdate.test(ccexpdate.value))
				{
					alert("Please enter your credit card's expiry date in the mm/yy form.");
					ccexpdate.focus();
					return false;
				}
			}
		}
		function Checkreturndate()
		{
			if(document.getElementById("returnflight").checked)
			{
				document.getElementById("returnflightdate").disabled = false;
			}
			else
			{
				document.getElementById("returnflightdate").disabled = true;
			}
		}
		function Checkmenu()
		{
			if(document.getElementById("firstclass").checked)
			{
				document.getElementById("lunchmenu").disabled = false;
			}
			else
			{
				document.getElementById("lunchmenu").disabled = true;
			}
		}
		function CheckCC()
		{
			if(document.getElementById("cctype").value == "-1")
			{
				document.getElementById("ccnum").disabled = true;
				document.getElementById("ccseccode").disabled = true;
				document.getElementById("ccexpdate").disabled = true;
			}
			else
			{
				document.getElementById("ccnum").disabled = false;
				document.getElementById("ccseccode").disabled = false;
				document.getElementById("ccexpdate").disabled = false;
			}
		}
	</script>
</head>
<header>

</header>
<body>
	<form name="daform" id="daform" action="/action.php" method="POST" onsubmit="return validateForm()">
		<table cellspacing="2" cellpadding="2" border="1">
			<tr>
				<th colspan="2">Passenger details.</th>
			</tr>
			<tr>
				<td>Name</td>
				<td><input type="text" id="name"></td>
			</tr>
			<tr>
				<td>City</td>
				<td><input type="text" id="city"></td>
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
				<td>Date of Birth</td>
				<td><input type="text" id="birthdate"></td>
			</tr>
			<tr>
				<td>Passport Number</td>
				<td><input type="text" id="passnum"></td>
			</tr>
			<tr>
				<th colspan="2">Fllight details.</th>
			</tr>
			<tr>
				<td>Flying from.</td>
				<td><input type="text" id="flyingfrom"></td>
			</tr>
			<tr>
				<td>Destination</td>
				<td><input type="text" id="destination"></td>
			</tr>
			<tr>
				<td>Flight Date</td>
				<td><input type="text" id="flightdate"></td>
			</tr>
			<tr>
				<td>Return Flight</td>
				<td><input type="checkbox" id="returnflight" onchange="Checkreturndate()">Yes</td>
			</tr>
			<tr>
				<td>Return Flight Date</td>
				<td><input type="text" id="returnflightdate" disabled></td>
			</tr>
			<tr>
				<td>Airline Company</td>
				<td>
					<select id="airline">
						<option value="-1"></option>
						<option value="1">AirSerbia</option>
						<option value="2">Lufthansa</option>
						<option value="3">British Airways</option>
					</select>
				</td>
			</tr>
			<tr>
				<td>First Class</td>
				<td><input type="checkbox" id="firstclass" onchange="Checkmenu()">Yes</td>
			</tr>
			<tr>
				<td>Lunch Menu</td>
				<td>
					<select id="lunchmenu" disabled>
						<option value="-1"></option>
						<option value="1">Vegetarian</option>
						<option value="2">Meat</option>
						<option value="3">Fish</option>
					</select>
				</td>
			</tr>
			<tr>
				<th colspan="2">Payment	details.</th>
			</tr>
			<tr>
				<td>Credit Card Type</td>
				<td>
					<select id="cctype" onchange="CheckCC()">
						<option value="-1" selected></option>
						<option value="1">Visa</option>
						<option value="2">Master</option>
						<option value="3">American Express</option>
					</select>
				</td>
			</tr>
			<tr>
				<td>Credit Card Number</td>
				<td><input type="text" id="ccnum" disabled></td>
			</tr>
			<tr>
				<td>Credit Card Security code</td>
				<td><input type="text" id="ccseccode" disabled></td>
			</tr>
			<tr>
				<td>Credit Card Expiry Date</td>
				<td><input type="text" id="ccexpdate" disabled></td>
			</tr>
			<tr>
				<td>Submit form</td>
				<td><input type="submit" value="submit form"></td>
			</tr>
			<tr>
				<td>Reset form</td>
				<td><input type="reset" value="reset form"></td>
			</tr>
		</table>
	</form>
</body>
<footer>

</footer>
</html>
