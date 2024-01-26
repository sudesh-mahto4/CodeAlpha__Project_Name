# CodeAlpha__Project_Name

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Age Calculator</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      text-align: center;
      margin: 50px;
    }
  </style>
</head>
<body>
  <h1>Age Calculator</h1>
  
  <form>
    <label for="dob">Enter your Date of Birth:</label>
    <input type="date" id="dob" required>
    <br>
    <button type="button" onclick="calculateAge()">Calculate Age</button>
  </form>

  <p id="result"></p>

  <script>
    function calculateAge() {
      // Get the selected date of birth
      var dobInput = document.getElementById("dob").value;
      var dob = new Date(dobInput);

      // Get the current date
      var currentDate = new Date();

      // Calculate the age
      var age = currentDate.getFullYear() - dob.getFullYear();

      // Check if the birthday has occurred this year
      if (currentDate.getMonth() < dob.getMonth() ||
          (currentDate.getMonth() === dob.getMonth() && currentDate.getDate() < dob.getDate())) {
        age--;
      }

      // Display the result
      var resultElement = document.getElementById("result");
      resultElement.innerHTML = "Your age is: " + age + " years.";
    }
  </script>
</body>
</html>
