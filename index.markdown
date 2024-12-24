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

<table id="login" class="table">
	<tr>
		<td>Userid</td> 
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
		"client2@shristigroup.com": { "hash": "wxyz", "redirect": "e5172ad1-bd20-4473-acc0-4b82336403e9" },
		"newerahospitalpvtltd": { "hash": "@123", "redirect": "dba9297c-e4bc-40cd-8ec0-0f83f3e96416" },
		"wockhearthospitalnagpur": { "hash": "@123", "redirect": "02ce3b96-20fa-49b0-a66e-4184b43022d5" },
		"kingswayhospitalnagpur": { "hash": "KWHOSP", "redirect": "a5849fd4-0628-444f-8c7c-5dd52c747954" },
		"paridhidiabetescentre": { "hash": "pdcr", "redirect": "eaf9f969-54d8-45c4-a86c-49cec8408f94" },
		"medishineraipur": { "hash": "medishineraipur", "redirect": "510bbd44-55e3-43d2-984f-88d305c0dca2" },
		"tiwariclinicallab": { "hash": "tcl", "redirect": "f93ce79c-e66c-4344-ae34-075c4c52843e" },
		"cardionhospital": { "hash": "chn", "redirect": "81ab5128-8ea3-4c2d-9007-a724f9453528" },
		"arnejaheartinstitute": { "hash": "ahin", "redirect": "8409d83d-8170-48db-af57-7d36234c839f" },
		"swarajdiagnosticcentre": { "hash": "sdcn", "redirect": "a40f9a61-746c-4096-b2db-f9d908fce110" },
		"drajaylanjewar": { "hash": "draln", "redirect": "b7d38cb1-e700-4cde-92b3-7042d5d62945" },
		
	}
	function checkNRedirectToClient() {
		var email = document.getElementById('email').value.trim();
		var hash = document.getElementById('hash').value.trim();


		if (clientData[email] && hash === clientData[email]["hash"]) {
			var newLocation =  window.location.href + clientData[email]["redirect"]
			//console.log(newLocation)
			window.location.href = newLocation;
			return false;
		}
		
		alert("No matching information found. Try again.")
	}
</script>
