
# Form validate

![version](https://img.shields.io/github/manifest-json/v/Natjo/formValidate)

Validation js native and accessible

```html
<form action="" novalidate="novalidate" role="form" aria-label="Contact information" data-mandatory="Mandatory field">

	<fieldset>

		<legend>Personal information</legend>

		<div class="field">
			<label for="">Name*</label>
			<input type="text" name="name" minlength="3" placeholder="3 caracters min" required aria-describedby="error-name" data-typemismatch="3 caracters min">
		</div>

		<div class="field">
			<label for="">Email*</label>
			<input type="email" required placeholder="Email" 
					 pattern="[a-z0-9._%+-]+@[a-z0-9.-]+\.[a-z]{2,4}$" aria-describedby="error-email" 
					 data-patternmismatch="Please type an email">
		</div>

		<div class="field">
			<label for="">Date*</label>
			<input type="date" required placeholder="jj/mm/aaaa" aria-describedby="error-date">
		</div>

		<div class="field">
			<label for="">Tel*</label>
			<input type="tel" required placeholder="(+xx) xxxxxxxx" pattern="^(?:0|\(?\+33\)?\s?|0033\s?)[1-79](?:[\.\-\s]?\d\d){4}$" aria-describedby="error-tel" data-patternmismatch="Tel number must be (+xx) xxxxxxxx">
		</div>

		<div class="field">
			<label>gender*</label>
			<select title="Select an option" required aria-describedby="error-gender">
				<option value="" hidden>Select</option>
				<option value="a">M</option>
				<option value="z">F</option>
			</select>
		</div>

		<div class="field">
			<label>Age*</label>
			<input type="number" required min="10" max="100" placeholder="Between 10 and 100" name="age" aria-describedby="error-age">
		</div>

		<div class="field">
			<label>Curriculum*</label>
			<input type="file" required name="curriculum" aria-describedby="error-curriculum">
		</div>

		<div class="field radio" role="group" aria-labelledby="country-label">
			<label id="country-label">Country*</label>
			<ul>
				<li>
					<input id="country-0" type="radio" name="test[]" value="" required aria-describedby="error-country">
					<label for="country-0">France</label>
				</li>
				<li>
					<input id="country-1" type="radio" name="test[]" value="" required aria-describedby="error-country">
					<label for="country-1">England</label>
				</li>
				<li>
					<input id="country-2" type="radio" name="test[]" value="" required aria-describedby="error-country">
					<label for="country-2">Russia</label>
				</li>
			</ul>
		</div>

		<div class="field">
			<label for="">Website*</label>
			<input type="url" required datat-type="date" placeholder="http://tld.com" name="website" require daria-describedby="error-website">
		</div>

		<div class="field">
			<label for="">Message*</label>
			<textarea name="msg" required aria-describedby="error-msg"></textarea>
		</div>

		<div class="field checkbox">
			
			<input id="newsletter" type="checkbox" name="newsletter" required aria-describedby="error-newsletter">
			<label for="newsletter">Newsletter*</label>
		</div>

		<div class="field">
			<label for="">User name</label>
			<input type="text" placeholder="User" name="user" required aria-describedby="error-user">
		</div>

		<div class="field">
			<label for="">Password</label>
			<input type="password" pattern="(?=.*\d)(?=.*[a-z])(?=.*[A-Z]).{8,}"
				placeholder="password" required
				name="password" aria-describedby="error-password">
			<small>
				At least on number, on uppercase letter, and 8 or more characters
			</small>
				
		</div>
 
	</fieldset>

	<div class="action">
		<input type="submit">
		<button type="reset">Reset</button>
	</div>

</form>

```

## Demo
[See codepen demo](https://codepen.io/natjo/pen/NmMzNd?editors=0011)


