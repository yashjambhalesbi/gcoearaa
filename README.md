<!DOCTYPE html>
<html>
  <head>
    <title>Calculator</title>
  </head>
  <body>
    <h1>Calculator</h1>
    <form method="POST" action="/calculate">
      <label for="num1">First number:</label>
      <input type="text" name="num1" id="num1"><br>
      <label for="num2">Second number:</label>
      <input type="text" name="num2" id="num2"><br>
      <label for="operation">Operation:</label>
      <select name="operation" id="operation">
        <option value="add">+</option>
        <option value="subtract">-</option>
        <option value="multiply">*</option>
        <option value="divide">/</option>
      </select><br>
      <input type="submit" value="Calculate">
    </form>
    {% if result %}
    <p>Result: {{ result }}</p>
    {% endif %}
  </body>
</html>
