<!DOCTYPE html>
<html>
<head>
</head>
<body>
    <p>Edit the sentence below:</p>
    <textarea id="textArea" name="text" rows="10" cols="30">The quick brown fox jumps over the lazy dog.</textarea><br>

    <label>Find what: </label>
    <input type="text" id="findWhat" placeholder="Enter the word"><br>

    <label>Replace with: </label>
    <input type="text" id="replaceWith" placeholder="Replace the word with">
    <button type="button" onclick="replaceWord();">Replace</button>
    <button type="button" onclick="clearNow();">Clear</button>
    
    <h2></h2>
    <label>Length of the sentence:</label>
    <p id="demo"> </p>
    
    <label>Uppercase</label>
    <p id="demo4"> </p>
    <label>Lowercase:</label>
    <p id="demo5"> </p>
    <label>Enter Word: </label>
    <input type="text" id="enterWord" placeholder="Enter the word"><br>
    <label>Does the word include in the sentence?:</label>
    <p id="demo2"> </p>
    <label>Search:</label>
    <p id="demo3"> </p>

    <script>
        function replaceWord() {
            let textArea = document.getElementById("textArea").value;
            let findWhat = document.getElementById("findWhat").value;
            let replaceWith = document.getElementById("replaceWith").value;
            let newText = textArea.replace(findWhat, replaceWith);
            document.getElementById("textArea").value = newText;
        }

        function clearNow() {
            document.getElementById("findWhat").value = "";
            document.getElementById("replaceWith").value = "";
            console.log('clear');
        }

        function formatText() {
            let text = document.getElementById("textArea").value;
            let searchWord = document.getElementById("enterWord").value;

            let length = text.length;
            let includesWord = text.includes(searchWord);
            let position = text.search(searchWord);
            let resultUppercase = text.toUpperCase();
            let resultLowercase = text.toLowerCase();

            document.getElementById("demo").innerHTML = length;
            document.getElementById("demo2").innerHTML = includesWord ? "Yes" : "No";
            document.getElementById("demo3").innerHTML = position !== -1 ? position : "Not found";
            document.getElementById("demo4").innerHTML = resultUppercase;
            document.getElementById("demo5").innerHTML = resultLowercase;
        }
		function resetNow() {
			document.getElementById("enterWord").value = "";
			console.log('clear');
    
		}
    </script>

    <button type="button" onclick="formatText();">Answer</button>
	<button type="button" onclick="resetNow();">Clear</button>

</body>
</html>
