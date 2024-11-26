---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: custom
---

<style>
	#table *{
		padding: 10px !important;
	}
</style>
<form
  action="https://formspree.io/f/mnnqgqdw"
  method="POST"
>
	<table id="table">
		<tr>
			<th> Select </th>
			<th> Name </th>
			<th> Price </th>
			<th> Quantity </th>
		</tr>
	{% for item in site.data.test %}
	<tr>
		<td>
			<input type="checkbox" onclick="var input = document.getElementById('{{ item.name }}'); if(this.checked){ input.disabled = false; input.focus();}else{input.disabled=true; input.value='';}" />

    	</td>
    	<td>
    		{{ item.name }}
    	</td>
    	<td>
    		{{ item.price }}
    	</td>
    	<td>
    		<input id="{{ item.name }}" name="{{ item.name }}" disabled="true"/>
    	</td>
    </tr>
    {% endfor %}
    </table>

    <button type="submit">Submit Order</button>

</form>
