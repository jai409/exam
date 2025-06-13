<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>JavaScript Assignment Tasks</title>
  <style>
    body {
      background-color: #111;
      color: #fff;
      font-family: Arial, sans-serif;
      padding: 20px;
    }
    .container {
      background: #1e1e1e;
      padding: 30px;
      border-radius: 10px;
    }
    h2 {
      margin-bottom: 10px;
    }
    .info-box {
      background-color: #0a6a8e;
      padding: 10px;
      margin: 20px 0;
    }
    .task-grid {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
      gap: 15px;
      margin-top: 20px;
    }
    button {
      background-color: #0693e3;
      color: #fff;
      padding: 12px;
      border: none;
      border-radius: 6px;
      cursor: pointer;
      font-size: 14px;
    }
    button:hover {
      background-color: #0aa6ff;
    }
  </style>
</head>
<body>
  <div class="container">
    <h2>STUDENT NAME : Jaijal George</h2>
    <h2>CURRENT DATE : 13/06/2025</h2>
    <h2>SUBJECT NAME : WEB TECHNOLOGY</h2>

    <div class="info-box">
      <strong>INFORMATION ABOUT ME:</strong> I am currently studying Computer Systems. I have a strong interest in technology, programming, and solving real-world problems through software. I'm eager to gain hands-on experience and grow as a professional in the IT field.
    </div>

    <h3>Task Details:</h3>
    <div class="task-grid">
      <button onclick="task1()">Task 1</button>
      <button onclick="task2()">Task 2</button>
      <button onclick="task3()">Task 3</button>
      <button onclick="task4()">Task 4</button>
      <button onclick="task5()">Task 5</button>
      <button onclick="task6()">Task 6</button>
      <button onclick="task7()">Task 7</button>
      <button onclick="task8()">Task 8</button>
      <button onclick="task9()">Task 9</button>
      <button onclick="task10()">Task 10</button>
    </div>
    <h3 style="margin-top: 40px;">Upload Your Screenshots:</h3>
      <input type="file" id="screenshotUpload" multiple accept="image/*">
      <div id="preview" style="margin-top: 20px; display: flex; flex-wrap: wrap; gap: 15px;"></div>
    </div>
  
    <h3 style="margin-top: 40px;">Mini project Title:</h3>
    <p><strong>Information:</strong></p>
    <ol>
      <li><strong>Problem Statement:</strong> Describe the problem your project addresses.</li>
      <li><strong>Objective:</strong> Explain the purpose of your project.</li>
      <li><strong>Goal:</strong> Define the end goals and intended outcomes of your project.</li>
      <li><strong>Result/Output:</strong> Outline the expected or actual results.</li>
    </ol>
  

  <script>
    function task1() {
      let a = prompt("Enter first value:");
      let b = prompt("Enter second value:");
      let op = prompt("Choose operation (+, -, *, /):");

      if (!isNaN(a) && !isNaN(b)) {
        a = parseFloat(a);
        b = parseFloat(b);
        let result;
        switch (op) {
          case "+": result = a + b; break;
          case "-": result = a - b; break;
          case "*": result = a * b; break;
          case "/": result = a / b; break;
          default: result = "Invalid operation";
        }
        alert("Result: " + result);
      } else {
        alert("String values detected. Performing string concatenation: " + a + b);
      }
    }

    function task2() {
      const str = prompt("Enter a string:");
      const reversed = str.split('').reverse().join('');
      const chars = 3rd char: ${str[2] || '-'}, 4th char: ${str[3] || '-'};
      alert("Reversed: " + reversed + "\n" + chars);
    }

    function task3() {
      const name = prompt("Enter your name:");
      const email = prompt("Enter your email:");
      const pass = prompt("Enter your password:");
      alert(Signup Info:\nName: ${name}\nEmail: ${email}\nPassword: ${pass});
    }

    function task4() {
      const person = {
        name: "Jaijal George",
        age: 21,
        gender: "Male"
      };
      alert(Person Object:\nName: ${person.name}\nAge: ${person.age}\nGender: ${person.gender});
    }

    let timer = 0;
    let interval;
    function task5() {
      const action = prompt("Timer: type 'start', 'stop', 'reset':").toLowerCase();
      switch (action) {
        case 'start':
          if (!interval) {
            interval = setInterval(() => {
              timer++;
              console.log("Time: " + timer + "s");
            }, 1000);
          }
          break;
        case 'stop':
          clearInterval(interval);
          interval = null;
          break;
        case 'reset':
          clearInterval(interval);
          interval = null;
          timer = 0;
          alert("Timer reset to 0.");
          break;
        default:
          alert("Invalid command.");
      }
    }

    function task6() {
      const fruits = ["Apple", "Banana", "Cherry", "Date"];
      alert("3rd fruit is: " + (fruits[2] || "Not available"));
    }

    function task7() {
      let a = parseFloat(prompt("Enter number 1:"));
      let b = parseFloat(prompt("Enter number 2:"));
      let op = prompt("Choose: sum / diff / mul / div");

      let result;
      switch (op) {
        case "sum": result = a + b; break;
        case "diff": result = a - b; break;
        case "mul": result = a * b; break;
        case "div": result = a / b; break;
        default: result = "Invalid choice.";
      }
      alert("Result: " + result);
    }

    function task8() {
      const arr = [10, 20, 30, 40];
      alert("Stored Array: " + arr.join(", "));
    }

    function task9() {
      const arr = [1, 2, 3, 4, 5];
      const doubled = arr.map(x => x * 2);
      alert("Doubled Array: " + doubled.join(", "));
    }

    function task10() {
      const input = prompt("Enter at least 10 characters:");
      if (input.length >= 10) {
        alert("10th character: " + input[9]);
      } else {
        alert("Too short! Please enter at least 10 characters.");
      }
    }
    // Screenshot upload and preview
    document.getElementById('screenshotUpload').addEventListener('change', function (event) {
      const preview = document.getElementById('preview');
      preview.innerHTML = ""; // Clear previous previews

      Array.from(event.target.files).forEach(file => {
        const reader = new FileReader();
        reader.onload = function (e) {
          const img = document.createElement('img');
          img.src = e.target.result;
          img.style.maxWidth = '200px';
          img.style.border = '1px solid #ccc';
          img.style.borderRadius = '8px';
          img.style.padding = '5px';
          preview.appendChild(img);
        };
        reader.readAsDataURL(file);
      });
    });
  </script>
</body>
</html># exam
