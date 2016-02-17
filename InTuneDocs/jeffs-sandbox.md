---
title: Jeff's Sandbox
ms.custom: na
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: tempfile
author: jeffgilb
---
## Pretty tables
This is what a striped table looks like.

<div class="table-wrapper">
<table class="table-striped">
	<caption>I am a test table caption!</caption>
	<thread>
		<tr>
			<th>Style</th>
			<th>Supported in table?</th>
		</tr>
	</thread>
	<tbody>
		<tr>
			<td><strong>Bold</strong> text </td>
			<td>Yes</td>
		</tr>
		<tr>
			<td><em>Italicized</em> text </td>
			<td>Yes</td>
		</tr>
		<tr>
			<td><del>Striked out</del> text </td>
			<td>Yes</td>
		</tr>
		<tr>
			<td>Inline <code>code</code></td>
			<td>Yes</td>
		</tr>		
		<tr>
			<td><a href="">Links</a></td>
			<td>Yes</td>
		</tr>
		<tr>
			<td>Lists, Alerts, Code Blocks, Images, Videos, Buttons, Giraffes</td>
			<td>No</td>
		</tr>
	</tbody>
</table>
</div>

## Dropdowns
### Flat list dropdowns
<p> Dropdowns may provide a flat list of links:
<div class="dropdown-container">
	<div class="dropdown">
		<select>
			<option value="<a href="https://docsmsftstage.azurewebsites.net/EM/index.html</a>">Option 1</option>
			<option value=".\jeffs-sandbox.html">Option 2</option>
			<option value="Option 3">.\jeffs-sandbox.html</option>
			<option value="Option 4">.\jeffs-sandbox.md</option>
			<option value="Option 5">jeffs-sandbox.md</option>
		</select>
	</div>
</p>

## Grouped list dropdowns
<p>Dropdowns may provide a grouped list of links:
<div class="dropdown-container">
	<div class="dropdown">
		<select>
			<optgroup label="Group A">
				<option value="Option A1">Option A1</option>
				<option value="Option A2">Option A2</option>
				<option value="Option A3">Option A3</option>
			</optgroup>
			<optgroup label="Group B">
				<option value="Option B1">Option B1</option>
				<option value="Option B2">Option B2</option>
				<option value="Option B3">Option B3</option>
			</optgroup>
		</select>
	</div>
</p>

### Different dropdown widths
<p>Dropdowns come in three explicit sizes (apart from teh default that sizes automatically): small, medium, large & full width:
<div class="dropdown-container dropdown-small">
	<div class="dropdown">
		<select>
			<option value="Option 1">Option 1</option>
			<option value="Option 2">Option 2</option>
			<option value="Option 3">Option 3</option>
		</select>
	</div>
<div><br /><br />
<div class="dropdown-container dropdown-medium">
	<div class="dropdown">
		<select>
			<option value="Option 1">Option 1</option>
			<option value="Option 2">Option 2</option>
			<option value="Option 3">Option 3</option>
		</select>
	</div>
<div><br /><br />
<div class="dropdown-container dropdown-large">
	<div class="dropdown">
		<select>
			<option value="Option 1">Option 1</option>
			<option value="Option 2">Option 2</option>
			<option value="Option 3">Option 3</option>
		</select>
	</div>
<div><br /><br />
<div class="dropdown-container dropdown-full">
	<div class="dropdown">
		<select>
			<option value="Option 1">Option 1</option>
			<option value="Option 2">Option 2</option>
			<option value="Option 3">Option 3</option>
		</select>
	</div>
<div>



### Buttons
The preferred markup for buttons is the <button> tag. However, you may also use the <a> tag to create buttons. It's eventually a question of semantics (i.e. "Is this thing I'm creating a button, or a link that looks button-like?").

<p>This is a default button:
	<button type="button">Hello</button>
</p>
<p>This is a small button:
	<button type="button" class="button-small">Hello</button>
</p>
<p>This is a big button:
	<button type="button" class="button-big">Hello</button>
</p>
<p>This is a big, disabled button:
	<button type="button" class="button-big" disbaled>Hello</button>
</p>
<p>This is a big button with an icon (don't forget to leave a space after the icon):
	<button type="button" class="button-big"><span class="icon icon-theme-day"> </span>Hello</button>
</p>
