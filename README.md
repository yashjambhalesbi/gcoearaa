from flask import Flask, render_template, request

app = Flask(__name__)

@app.route('/')
def index():
    return render_template('calculator.html')

@app.route('/calculate', methods=['POST'])
def calculate():
    num1 = request.form['num1']
    num2 = request.form['num2']
    operation = request.form['operation']
    
    result = 0
    
    if operation == 'add':
        result = float(num1) + float(num2)
    elif operation == 'subtract':
        result = float(num1) - float(num2)
    elif operation == 'multiply':
        result = float(num1) * float(num2)
    elif operation == 'divide':
        result = float(num1) / float(num2)
    
    return render_template('calculator.html', result=result)

if __name__ == '__main__':
    app.run(debug=True)

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
