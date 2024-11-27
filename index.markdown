---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: custom
title: Bulk Order
---

<style>
  .table * {
    padding: 10px !important;
  }
</style>
<p>
Use below Information for testing: <br/>
Email: client1@shristigroup.com Hash: abcd<br/>
Email: client2@shristigroup.com Hash: wxyz<br/>
</p>
<table id="login" class="table">
	<tr>
		<td>Email</td> 
		<td><input id="email"/></td>
	</tr>
	<tr>
		<td>Code</td>
		<td><input id="hash"/></td>
	</tr>
	<tr>
		<td colspan="2">
			<div class="ec-size ec-size--xl">
				<div class="ec-store">
					<div class="form-control form-control--button form-control--secondary btn-get-direction">
						<a class="form-control__button" href="#" onclick="checkNRedirectToClient(); return false;" target="_blank">
							<span class="form-control__button-text">
								<span>Submit</span>
							</span>
						</a>
					</div>
				</div>
			</div>
		</td>
	</tr>
</table>

<script>
	clientData = {
		"client1@shristigroup.com": { "hash": "abcd", "redirect": "8d92e8d3-864e-48be-815c-af415a70600f" },
		"client2@shristigroup.com": { "hash": "wxyz", "redirect": "e5172ad1-bd20-4473-acc0-4b82336403e9" }
	}
	function checkNRedirectToClient() {
		var email = document.getElementById('email').value.trim();
		var hash = document.getElementById('hash').value.trim();

		if (!clientData[email]) {
			alert("Email not found")
			return false;
		}

		if (hash === clientData[email]["hash"]) {
			var newLocation =  window.location.href + clientData[email]["redirect"]
			//console.log(newLocation)
			window.location.href = newLocation;
			return false;
		}
		
		alert("No matching information found. Try again.")
	}
</script>
