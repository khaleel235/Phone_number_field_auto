# Phone_number_field_auto
Entering phone number auto call back with " ( ) " "-" and fixed digits
/* form-field here */
<input style="width:220px" onkeydown="phoneNumberFormatter()" type="tel" class="main-form-field phone-number2 w-input" maxlength="256" name="phone" data-name="phone" placeholder="Phone Number (optional)" id="phonenum">


<script>
      function formatPhoneNumber(value) {
        if (!value) return value;
        const phoneNumber = value.replace(/[^\d]/g, '');
        const phoneNumberLength = phoneNumber.length;
        if (phoneNumberLength < 4) return phoneNumber;
        if (phoneNumberLength < 7) {
          return `(${phoneNumber.slice(0, 3)}) ${phoneNumber.slice(3)}`;
        }
        return `(${phoneNumber.slice(0, 3)}) ${phoneNumber.slice(
          3,
          6
        )}-${phoneNumber.slice(6, 9)}`;
      }

      function phoneNumberFormatter() {
        const inputField = document.getElementById('phonenum');
        const formattedInputValue = formatPhoneNumber(inputField.value);
        inputField.value = formattedInputValue;
      }
</script>
