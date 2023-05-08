<!DOCTYPE html>
<html>
<head>
	<title>Student Information Form</title>
</head>
<body>
	<h1>Student Information Form</h1>
	<form action="submit.php" method="post">
		<label for="name">Student Name:</label>
		<input type="text" id="name" name="name" required><br><br>
		
		<label for="email">Student Email:</label>
		<input type="email" id="email" name="email" required><br><br>
		
		<label for="parent-email">Parent Email:</label>
		<input type="email" id="parent-email" name="parent-email" required><br><br>
		
		<label for="roll-id">Roll ID:</label>
		<input type="text" id="roll-id" name="roll-id" required><br><br>
		
		<input type="submit" value="Submit">
	</form>
</body>
</html>
<?php
// Get the form data
$name = $_POST['name'];
$email = $_POST['email'];
$parent_email = $_POST['parent-email'];
$roll_id = $_POST['roll-id'];

// Open the text file for writing
$file = fopen("student_info.txt", "a");

// Write the student info to the file
fwrite($file, "$name\t$email\t$parent_email\t$roll_id\n");

// Close the file
fclose($file);

// Redirect the user back to the form
header("Location: index.html");
exit();
?>
