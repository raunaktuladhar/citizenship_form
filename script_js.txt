document.addEventListener("DOMContentLoaded", function () {
    document.getElementById("citizenshipForm").addEventListener("submit", function (event) {
        let isValid = true;

        // Get form values
        let fullName = document.getElementById("fullName").value.trim();
        let sex = document.getElementById("sex").value;
        let birthPlace = document.getElementById("birthPlace").value.trim();
        let permanentAddress = document.getElementById("permanentAddress").value.trim();
        let dob = document.getElementById("dob").value;
        let fatherName = document.getElementById("fatherName").value.trim();
        let motherName = document.getElementById("motherName").value.trim();
        let wardNo = document.getElementById("wardNo").value.trim();
        let applicantName = document.getElementById("applicantName").value.trim();

        // Validation rules
        if (fullName === "") {
            alert("कृपया नाम, थर प्रविष्ट गर्नुहोस्।");
            isValid = false;
        }
        if (sex === "") {
            alert("कृपया लिङ्ग चयन गर्नुहोस्।");
            isValid = false;
        }
        if (birthPlace === "") {
            alert("कृपया जन्म स्थान प्रविष्ट गर्नुहोस्।");
            isValid = false;
        }
        if (permanentAddress === "") {
            alert("कृपया स्थायी ठेगाना प्रविष्ट गर्नुहोस्।");
            isValid = false;
        }
        if (dob === "") {
            alert("कृपया जन्म मिति प्रविष्ट गर्नुहोस्।");
            isValid = false;
        }
        if (fatherName === "") {
            alert("कृपया बुबाको नाम, थर प्रविष्ट गर्नुहोस्।");
            isValid = false;
        }
        if (motherName === "") {
            alert("कृपया आमाको नाम, थर प्रविष्ट गर्नुहोस्।");
            isValid = false;
        }
        if (wardNo === "") {
            alert("कृपया वडा नम्बर प्रविष्ट गर्नुहोस्।");
            isValid = false;
        }
        if (applicantName === "") {
            alert("कृपया निवेदकको नाम, थर प्रविष्ट गर्नुहोस्।");
            isValid = false;
        }

        // Prevent form submission if validation fails
        if (!isValid) {
            event.preventDefault();
        }
    });
});
