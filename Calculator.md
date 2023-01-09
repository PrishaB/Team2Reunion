## Calculator FRQ 

### You can use this feature to do some basic calculations :)

<button onclick="calculator()">Enter Equation</button>

<p> The answer to your equation is: <p id="answer"> </p>

<script>
  
  function calculator() {
    let expression = prompt("Enter the equation you'd like to have solved");
    const urlStart = "https://localhost:8085/api/calculator/";
    const url = urlStart + expression;

    console.log(url); 

    fetch(url)
      .then(res => res.json())
      .then(data => {
        console.log(data);
        
        document.getElementById("answer").innerHTML = data.result; 
      
      })
      
}
</script>

<style> 
button {
	width: 120px;
	height: 40px;
	font-size: 15px;
	background-color: #43B4E5;
	color: #fff;
	border: none;
	cursor: pointer;
}

p {
  font-size: 20px;
  color: #010000;
}
</style>