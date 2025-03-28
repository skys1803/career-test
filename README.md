# career-test
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Career Compass Test</title>
    <style>
        body { font-family: Arial, sans-serif; text-align: center; margin: 20px; }
        .question { margin: 20px 0; }
        .result { display: none; font-weight: bold; margin-top: 20px; }
        button { padding: 10px 15px; margin-top: 20px; cursor: pointer; }
    </style>
</head>
<body>
    <h1>Career Compass: Aptitude Test</h1>
    <form id="careerTest">
        <div class="question">
            <p>1. How do you prefer to work?</p>
            <label><input type="radio" name="q1" value="A"> Structured and organized</label><br>
            <label><input type="radio" name="q1" value="B"> Flexible and creative</label><br>
            <label><input type="radio" name="q1" value="C"> Leading and managing</label><br>
            <label><input type="radio" name="q1" value="D"> Independently solving problems</label>
        </div>
        <div class="question">
            <p>2. Which subject do you excel at?</p>
            <label><input type="radio" name="q2" value="A"> Math/Physics</label><br>
            <label><input type="radio" name="q2" value="B"> Art/Literature</label><br>
            <label><input type="radio" name="q2" value="C"> Business/Leadership</label><br>
            <label><input type="radio" name="q2" value="D"> Biology/Chemistry</label>
        </div>
        <button type="button" onclick="calculateResult()">Get Results</button>
    </form>
    <p class="result" id="resultText"></p>

    <script>
        function calculateResult() {
            let scores = { A: 0, B: 0, C: 0, D: 0 };
            let form = document.getElementById("careerTest");
            let choices = form.getElementsByTagName("input");

            for (let choice of choices) {
                if (choice.checked) {
                    scores[choice.value]++;
                }
            }

            let maxCategory = Object.keys(scores).reduce((a, b) => scores[a] > scores[b] ? a : b);
            let careerPaths = {
                A: "Technology, Engineering, Finance",
                B: "Media, Design, Arts",
                C: "Marketing, Management, Entrepreneurship",
                D: "Medical, Scientific, Environmental"
            };

            document.getElementById("resultText").innerText = "Your recommended career path: " + careerPaths[maxCategory];
            document.getElementById("resultText").style.display = "block";
        }
    </script>
</body>
</html>

