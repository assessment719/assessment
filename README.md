<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>University Selection Example</title>
    <style>
        body {
            font-family: Arial, sans-serif;
        }

        .container {
            margin: 20px;
        }

        label {
            display: block;
            margin-top: 20px;
        }

        select, input[type="number"] {
            width: 100%;
            padding: 10px;
            margin-top: 5px;
        }

        .university-box {
            margin-top: 20px;
            font-weight: bold;
            text-align: center;
            border: 2px solid green;
            padding: 10px;
        }

        .button-container {
            display: flex;
            justify-content: center;
            margin-bottom: 20px;
        }

        .button {
            margin: 0 10px;
            padding: 10px 20px;
            cursor: pointer;
            background-color: #007bff;
            color: white;
            border: none;
            border-radius: 5px;
            font-size: 16px;
        }

        .button.active {
            background-color: green;
        }
    </style>
</head>
<body>
    <h1>One Stop Solution For Assessment By Piyobroto Das</h1>
    <div class="button-container">
        <button class="button active" id="form1Button">1. Academic Requirement</button>
        <button class="button" id="form2Button">2. Standard 12 English Waiver</button>
        <button class="button" id="form3Button">3. English Language Test</button>
    </div>

    <!-- First University Form -->
    <div class="container form-container" id="form1">
        <h2>1. Academic Requirement</h2>
        <form id="universityForm1">
            <label for="educationLevel1">Select Level of Study:</label>
            <select id="educationLevel1">
                <option value="Undergraduate">Undergraduate</option>
                <option value="Postgraduate">Postgraduate</option>
            </select>
            <label for="educationSystem1">Select Educational Institutions:</label>
            <select id="educationSystem1">
                <!-- Options will be dynamically populated based on the selected educationLevel1 -->
            </select>

            <label for="slider1">Enter Marks:</label>
            <input type="number" id="slider1" min="0" max="100" value="0">

            <button type="submit">Submit</button>
        </form>
        <div id="university1" class="university-box"></div>
        <div id="university2" class="university-box"></div>
        <div id="university3" class="university-box"></div>
    </div>

    <!-- Second University Form -->
    <div class="container form-container" id="form2" style="display: none;">
        <h2>2. Standard 12 English Waiver</h2>
        <form id="universityForm2">
            <label for="educationLevel2">Select Level of Study:</label>
            <select id="educationLevel2">
                <option value="Undergraduate">Undergraduate</option>
                <option value="Postgraduate">Postgraduate</option>
            </select>
            <label for="educationSystem2">Select Educational Institutions:</label>
            <select id="educationSystem2">
                <!-- Options will be dynamically populated based on the selected educationLevel2 -->
            </select>

            <label for="slider2">Enter Marks:</label>
            <input type="number" id="slider2" min="0" max="100" value="0">

            <button type="submit">Submit</button>
        </form>
        <div id="university4" class="university-box"></div>
        <div id="university5" class="university-box"></div>
        <div id="university6" class="university-box"></div>
    </div>

    <!-- Third University Form -->
    <div class="container form-container" id="form3" style="display: none;">
        <h2>3. English Language Test</h2>
        <form id="universityForm3">
            <label for="educationLevel3">Select Level of Study:</label>
            <select id="educationLevel3">
                <option value="Undergraduate">Undergraduate</option>
                <option value="Postgraduate">Postgraduate</option>
            </select>
            <label for="educationSystem3">Select English Language Test:</label>
            <select id="educationSystem3">
                <option value="IELTS">IELTS</option>
                <option value="Pearson Test of English">Pearson Test of English</option>
                <option value="TOEFL">TOEFL</option>
            </select>

            <label for="slider3">Enter Overall Marks:</label>
            <input type="number" id="slider3" min="0" max="100" value="0">

            <label for="slider4">Enter Reading Marks:</label>
            <input type="number" id="slider4" min="0" max="100" value="0">

            <label for="slider5">Enter Writing Marks:</label>
            <input type="number" id="slider5" min="0" max="100" value="0">

            <label for="slider6">Enter Listening Marks:</label>
            <input type="number" id="slider6" min="0" max="100" value="0">

            <label for="slider7">Enter Speaking Marks:</label>
            <input type="number" id="slider7" min="0" max="100" value="0">

            <button type="submit">Submit</button>
        </form>
        <div id="university7" class="university-box"></div>
        <div id="university8" class="university-box"></div>
        <div id="university9" class="university-box"></div>
        <div id="university10" class="university-box"></div>
        <div id="university11" class="university-box"></div>
    </div>

<script>
    document.addEventListener('DOMContentLoaded', function() {
        const form1Button = document.getElementById('form1Button');
        const form2Button = document.getElementById('form2Button');
        const form3Button = document.getElementById('form3Button');
        const form1 = document.getElementById('form1');
        const form2 = document.getElementById('form2');
        const form3 = document.getElementById('form3');

        form1Button.addEventListener('click', function() {
            form1.style.display = 'block';
            form2.style.display = 'none';
            form3.style.display = 'none';
            form1Button.classList.add('active');
            form2Button.classList.remove('active');
            form3Button.classList.remove('active');
        });

        form2Button.addEventListener('click', function() {
            form1.style.display = 'none';
            form2.style.display = 'block';
            form3.style.display = 'none';
            form1Button.classList.remove('active');
            form2Button.classList.add('active');
            form3Button.classList.remove('active');
        });

        form3Button.addEventListener('click', function() {
            form1.style.display = 'none';
            form2.style.display = 'none';
            form3.style.display = 'block';
            form1Button.classList.remove('active');
            form2Button.classList.remove('active');
            form3Button.classList.add('active');
        });

        const universityForm1 = document.getElementById('universityForm1');
        const educationLevel1 = document.getElementById('educationLevel1');
        const educationSystem1 = document.getElementById('educationSystem1');
        const slider1 = document.getElementById('slider1');
        const universityDiv1 = document.getElementById('university1');
        const universityDiv2 = document.getElementById('university2');
        const universityDiv3 = document.getElementById('university3');

        const updateEducationSystemOptions1 = () => {
            const selectedLevel = educationLevel1.value;
            educationSystem1.innerHTML = ''; // Clearing previous options
            if (selectedLevel === 'Undergraduate') {
                const options = ['Board of Intermediate Education, Andhra Pradesh', 'Government of Kerala Board of Higher Secondary Examinations'];
                options.forEach(option => {
                    const optionElement = document.createElement('option');
                    optionElement.textContent = option;
                    optionElement.value = option;
                    educationSystem1.appendChild(optionElement);
                });
            } else if (selectedLevel === 'Postgraduate') {
                const options = ['University of Calcutta', 'Jadavpur University'];
                options.forEach(option => {
                    const optionElement = document.createElement('option');
                    optionElement.textContent = option;
                    optionElement.value = option;
                    educationSystem1.appendChild(optionElement);
                });
            }
        };

        educationLevel1.addEventListener('change', updateEducationSystemOptions1);
        updateEducationSystemOptions1(); // Initial population of options

        const universityForm2 = document.getElementById('universityForm2');
        const educationLevel2 = document.getElementById('educationLevel2');
        const educationSystem2 = document.getElementById('educationSystem2');
        const slider2 = document.getElementById('slider2');
        const universityDiv4 = document.getElementById('university4');
        const universityDiv5 = document.getElementById('university5');
        const universityDiv6 = document.getElementById('university6');

        const updateEducationSystemOptions2 = () => {
            const selectedLevel = educationLevel2.value;
            educationSystem2.innerHTML = ''; // Clearing previous options
            if (selectedLevel === 'Undergraduate') {
                const options = ['1. Board of Intermediate Education, Andhra Pradesh', '2. Government of Kerala Board of Higher Secondary Examinations'];
                options.forEach(option => {
                    const optionElement = document.createElement('option');
                    optionElement.textContent = option;
                    optionElement.value = option;
                    educationSystem2.appendChild(optionElement);
                });
            } else if (selectedLevel === 'Postgraduate') {
                const options = ['A. Board of Intermediate Education, Andhra Pradesh', 'B. Government of Kerala Board of Higher Secondary Examinations'];
                options.forEach(option => {
                    const optionElement = document.createElement('option');
                    optionElement.textContent = option;
                    optionElement.value = option;
                    educationSystem2.appendChild(optionElement);
                });
            }
        };

        educationLevel2.addEventListener('change', updateEducationSystemOptions2);
        updateEducationSystemOptions2(); // Initial population of options

        const universityForm3 = document.getElementById('universityForm3');
        const educationLevel3 = document.getElementById('educationLevel3');
        const educationSystem3 = document.getElementById('educationSystem3');
        const slider3 = document.getElementById('slider3');
        const slider4 = document.getElementById('slider4');
        const slider5 = document.getElementById('slider5');
        const slider6 = document.getElementById('slider6');
        const slider7 = document.getElementById('slider7');
        const universityDiv7 = document.getElementById('university7');
        const universityDiv8 = document.getElementById('university8');
        const universityDiv9 = document.getElementById('university9');
        const universityDiv10 = document.getElementById('university10');
        const universityDiv11 = document.getElementById('university11');

        const updateEducationSystemOptions3 = () => {
            const selectedLevel = educationLevel3.value;
            educationSystem3.innerHTML = ''; // Clearing previous options
            if (selectedLevel === 'Undergraduate') {
                const options = ['1. IELTS', '2. Pearson Test of English', '3. TOEFL'];
                options.forEach(option => {
                    const optionElement = document.createElement('option');
                    optionElement.textContent = option;
                    optionElement.value = option;
                    educationSystem3.appendChild(optionElement);
                });
            } else if (selectedLevel === 'Postgraduate') {
                const options = ['A. IELTS', 'B. Pearson Test of English', 'C. TOEFL'];
                options.forEach(option => {
                    const optionElement = document.createElement('option');
                    optionElement.textContent = option;
                    optionElement.value = option;
                    educationSystem3.appendChild(optionElement);
                });
            }
        };

        educationLevel3.addEventListener('change', updateEducationSystemOptions3);
        updateEducationSystemOptions3(); // Initial population of options

        const handleFormSubmit1 = function(event) {
            event.preventDefault(); // Prevent the form from submitting normally

            const inputValue1 = parseInt(slider1.value);
            let universityName1 = '';
            let universityName2 = '';
            let universityName3 = '';

            if (educationLevel1.value === 'Undergraduate' && educationSystem1.value === 'Board of Intermediate Education, Andhra Pradesh') {
                if (inputValue1 >= 90) {
                    universityName1 = 'Abertay University';
                    universityName2 = 'Anglia Ruskin University';
                } else if (inputValue1 >= 70) {
                    universityName1 = 'University of Bradford';
                    universityName2 = 'Another University for CBSE with 0-69 range';
                } else {
                    universityName1 = 'Another University for CBSE with 0-59 range';
                }
            } else if (educationLevel1.value === 'Postgraduate' && educationSystem1.value === 'Jadavpur University') {
                if (inputValue1 >= 60) {
                    universityName1 = 'Aberystwyth University';
                    universityName2 = 'London Metropolitan University';
                    universityName3 = 'De Montford University';
                } else if (inputValue1 >= 50) {
                    universityName1 = 'University of Bradford';
                    universityName2 = 'Another University for CISCE with 0-49 range';
                } else {
                    universityName1 = 'Another University for CISCE with 0-49 range';
                }
            }

            universityDiv1.textContent = universityName1;
            universityDiv2.textContent = universityName2;
            universityDiv3.textContent = universityName3;
        };

        universityForm1.addEventListener('submit', handleFormSubmit1);

        const handleFormSubmit2 = function(event) {
            event.preventDefault(); // Prevent the form from submitting normally

            const inputValue2 = parseInt(slider2.value);
            let universityName4 = '';
            let universityName5 = '';
            let universityName6 = '';

            if (educationLevel2.value === 'Undergraduate' && educationSystem2.value === '1. Board of Intermediate Education, Andhra Pradesh') {
                if (inputValue2 >= 80) {
                    universityName4 = 'Abertay University';
                    universityName5 = 'Anglia Ruskin University';
                } else if (inputValue2 >= 70) {
                    universityName4 = 'University of Bradford';
                    universityName5 = 'Another University for CBSE with 0-69 range';
                } else {
                    universityName4 = 'Another University for CBSE with 0-59 range';
                }
            } else if (educationLevel2.value === 'Postgraduate' && educationSystem2.value === 'B. Government of Kerala Board of Higher Secondary Examinations') {
                if (inputValue2 >= 60) {
                    universityName4 = 'Aberystwyth University';
                    universityName5 = 'London Metropolitan University';
                    universityName6 = 'De Montford University';
                } else if (inputValue2 >= 50) {
                    universityName4 = 'University of Bradford';
                    universityName5 = 'Another University for CISCE with 0-49 range';
                } else {
                    universityName4 = 'Another University for CISCE with 0-49 range';
                }
            }

            universityDiv4.textContent = universityName4;
            universityDiv5.textContent = universityName5;
            universityDiv6.textContent = universityName6;
        };

        universityForm2.addEventListener('submit', handleFormSubmit2);

        const handleFormSubmit3 = function(event) {
            event.preventDefault(); // Prevent the form from submitting normally

            const inputValue3 = parseInt(slider3.value);
            const inputValue4 = parseInt(slider4.value);
            const inputValue5 = parseInt(slider5.value);
            const inputValue6 = parseInt(slider6.value);
            const inputValue7 = parseInt(slider7.value);
            let universityName7 = '';
            let universityName8 = '';

            if (educationLevel3.value === 'Undergraduate' && educationSystem3.value === '1. IELTS') {
                if (inputValue3 >= 90 && inputValue4 >= 80 && inputValue5 >= 70 && inputValue6 >= 60 && inputValue7 >= 50) {
                    universityName7 = 'University of Birmingham';
                    universityName8 = 'University of Westminster';
                } else if (inputValue3 >= 80 && inputValue4 >= 70 && inputValue5 >= 60 && inputValue6 >= 50 && inputValue7 >= 40) {
                    universityName7 = 'University of Lincoln';
                    universityName8 = 'University of Liverpool';
                }
            } else if (educationLevel3.value === 'Postgraduate' && educationSystem3.value === 'A. IELTS') {
                if (inputValue3 >= 90 && inputValue4 >= 80 && inputValue5 >= 70 && inputValue6 >= 60 && inputValue7 >= 50) {
                    universityName7 = 'University of Birmingham';
                    universityName8 = 'University of Westminster';
                } else if (inputValue3 >= 80 && inputValue4 >= 70 && inputValue5 >= 60 && inputValue6 >= 50 && inputValue7 >= 40) {
                    universityName7 = 'University of Lincoln';
                    universityName8 = 'University of Liverpool';
                }
            } else if (educationLevel3.value === 'Undergraduate' && educationSystem3.value === '2. Pearson Test of English') {
                if (inputValue3 >= 90 && inputValue4 >= 80 && inputValue5 >= 70 && inputValue6 >= 60 && inputValue7 >= 50) {
                    universityName7 = 'University of Birmingham';
                    universityName8 = 'University of Westminster';
                } else if (inputValue3 >= 80 && inputValue4 >= 70 && inputValue5 >= 60 && inputValue6 >= 50 && inputValue7 >= 40) {
                    universityName7 = 'University of Lincoln';
                    universityName8 = 'University of Liverpool';
                }
            } else if (educationLevel3.value === 'Postgraduate' && educationSystem3.value === 'C. TOEFL') {
                if (inputValue3 >= 90 && inputValue4 >= 80 && inputValue5 >= 70 && inputValue6 >= 60 && inputValue7 >= 50) {
                    universityName7 = 'University of Birmingham';
                    universityName8 = 'University of Westminster';
                } else if (inputValue3 >= 80 && inputValue4 >= 70 && inputValue5 >= 60 && inputValue6 >= 50 && inputValue7 >= 40) {
                    universityName7 = 'University of Lincoln';
                    universityName8 = 'University of Liverpool';
                }
            } else if (educationLevel3.value === 'Undergraduate' && educationSystem3.value === 'TOEFL') {
                if (inputValue3 >= 95 && inputValue4 >= 85 && inputValue5 >= 75 && inputValue6 >= 65 && inputValue7 >= 55) {
                    universityName7 = 'University of Birmingham';
                    universityName8 = 'University of Westminster';
                } else if (inputValue3 >= 85 && inputValue4 >= 75 && inputValue5 >= 65 && inputValue6 >= 55 && inputValue7 >= 45) {
                    universityName7 = 'University of Lincoln';
                    universityName8 = 'University of Liverpool';
                }
            } else if (educationLevel3.value === 'Postgraduate' && educationSystem3.value === 'TOEFL') {
                if (inputValue3 >= 95 && inputValue4 >= 85 && inputValue5 >= 75 && inputValue6 >= 65 && inputValue7 >= 55) {
                    universityName7 = 'University of Birmingham';
                    universityName8 = 'University of Westminster';
                } else if (inputValue3 >= 85 && inputValue4 >= 75 && inputValue5 >= 65 && inputValue6 >= 55 && inputValue7 >= 45) {
                    universityName7 = 'University of Lincoln';
                    universityName8 = 'University of Liverpool';
                }
            }

            universityDiv7.textContent = universityName7;
            universityDiv8.textContent = universityName8;
        };

        universityForm3.addEventListener('submit', handleFormSubmit3);
    });
</script>
</body>
</html>
