<?php
if ($_SERVER["REQUEST_METHOD"] == "POST") {
    $fullName = $_POST['fullName'];
    $sex = $_POST['sex'];
    $birthPlace = $_POST['birthPlace'];
    $permanentAddress = $_POST['permanentAddress'];
    $dob = $_POST['dob'];
    $fatherName = $_POST['fatherName'];
    $motherName = $_POST['motherName'];
    $spouseName = $_POST['spouseName'];
    // $guardianName = $_POST['guardianName'];
    $wardNo = $_POST['wardNo'];
    $applicantName = $_POST['applicantName'];

    // Database Connection
    $conn = new mysqli("localhost", "root", "", "citizenship_db");

    // Check Connection
    if ($conn->connect_error) {
        die("Connection failed: " . $conn->connect_error);
    }

    // Prepare SQL Query
    $sql = "INSERT INTO citizenship_form (Full_Name, Sex, Birth_Place, Permanent_Address, Ward_No, Date_Of_Birth, Father_Name, Mother_Name, Spouse_Name, Guardian_Name, Applicant_Name) 
            VALUES ('$fullName', '$sex', '$birthPlace', '$permanentAddress', '$wardNo', '$dob', '$fatherName', '$motherName', '$spouseName', '$guardianName','$applicantName')";

    // Execute Query
    $result = $conn->query($sql);

    // Display Message
    echo $result ? "<h2>फारम सफलतापूर्वक पेश गरियो!</h2>" : "त्रुटि: " . $conn->error;

    // Close Connection
    $conn->close();

    echo "<h2>फारम सफलतापूर्वक पेश गरियो!</h2>";
    echo "<p><strong>नाम, थर:</strong> $fullName</p>";
    echo "<p><strong>लिङ्ग:</strong> $sex</p>";
    echo "<p><strong>जन्म स्थान:</strong> $birthPlace</p>";
    echo "<p><strong>स्थायी ठेगाना:</strong> $permanentAddress</p>";
    echo "<p><strong>जन्म मिति:</strong> $dob</p>";
    echo "<p><strong>बुबाको नाम, थर:</strong> $fatherName</p>";
    echo "<p><strong>आमाको नाम, थर:</strong> $motherName</p>";
    
    if (!empty($spouseName)) {
        echo "<p><strong>पति/पत्नीको नाम, थर:</strong> $spouseName</p>";
    }

    echo "<p><strong>गाउँपालिका/नगरपालिका वडा नं:</strong> $wardNo</p>";
    echo "<p><strong>निवेदकको नाम, थर:</strong> $applicantName</p>";
}
?>
