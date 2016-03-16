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

## iFrame
<iframe width="730" height="800" src="https://onedrive.live.com/edit.aspx?cid=15f03658bc93f824&page=view&resid=15F03658BC93F824!41614&parId=15F03658BC93F824!145&app=Excel" frameborder="0" allowfullscreen></iframe>


> [!NOTE]
> I am a NOTE

> [!IMPORTANT]
> I am IMPORTANT

<div class="alert alert-warning">
	<h5><span class="icon icon-warning"></span> Warning</h5>
	<p>Nothing on this page is supported for OPS because they're not approved markdown extensions!</p>
</div>


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

## Doc-level options
The Doc-level Options component allows authors to embed other UI components (in this version: dropdowns & buttons) within conceptual documents to enable scenarios like language and platform switching. It is presented right below author metadata at the start of a conceptual document.

<ul class="document-ui">
	<li>
		<div class="dropdown-container">
			<label for="dropdown">Pick an option</label>
			<div class="dropdown">
				<select>
					<option value="option-a">Option A</option>
					<option value="option-b">Option B</option>
				</select>
			</div>
		</div>
	</li>
	<li>
		<div class="dropdown-container">
			<label for="dropdown">And another</label>
			<div class="dropdown">
				<select>
					<option value="option-c">Option C</option>
					<option value="option-d">Option D</option>
				</select>
			</div>
		</div>
	</li>
	<li>
		<button type="button" class="button-small">Button</button>
	</li>
</ul>

## Dropdowns
### Flat list dropdowns
<p> Dropdowns may provide a flat list of links:
<div class="dropdown-container">
	<div class="dropdown">
		<select>
			<option value="<a href="https://docsmsftstage.azurewebsites.net/EM/index.html</a>"Option 1</option>
			<option value=".\jeffs-sandbox.html">Option 2</option>
			<option value="jeffs-sandbox.html">Option 3</option>
			<option value=".\jeffs-sandbox.md">Option 4</option>
			<option value="jeffs-sandbox.md">Option 5</option>
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



## Buttons
The preferred markup for buttons is the button tag. However, you may also use the <a> tag to create buttons. It's eventually a question of semantics (i.e. "Is this thing I'm creating a button, or a link that looks button-like?").

<p>This is a default button:
	<button type="button">Default</button>
</p>
<p>This is a small button:
	<button type="button" class="button-small">Small</button>
</p>
<p>This is a big button:
	<button type="button" class="button-big">Big</button>
</p>
<p>This is a big, disabled button:
	<button type="button" class="button-big" disbaled>Big Disabled</button>
</p>
<p>This is a big button with an icon (don't forget to leave a space after the icon):
	<button type="button" class="button-big"><span class="icon icon-theme-day"> </span>Big With Icon</button>
</p>
