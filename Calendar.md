## Calendar FRQ

<script>

function getYear(){
    let inputYear = document.getElementById("inputYear").value;
    return inputYear;
}

function isLeapYear(yearparam) {
    
    result = document.getElementById("isLeapYearResult");

    // Fetch data from API
    fetch('https://hetvitrivedi.tk/api/calendar/isLeapYear/' + yearparam)
    .then(response => response.json())
    .then(data => {

        console.log(data);

        result.innerHTML = "Is " + yearparam + " a leap year: " + data.isLeapYear;

    })
}

function firstDayOfYear(yearparam) {

    result = document.getElementById("theFirstDayOfYear");
    fetch('https://localhost:8085/api/calendar/firstDayOfYear/' + yearparam)
    .then(response => response.json())
    .then(data => {
        
        console.log(data);

        result.innerHTML = "The first day of the year" + yearparam + "has the numerical value: " + data.firstDayOfYear;
    })
}

</script>

### Want to know if a year is a leap year? Input a number below and find out!
<input id="inputYear" placeholder="Input a Year">
<button onclick="isLeapYear(getYear())">Submit</button>
<p id="isLeapYearResult"></p>

### Want to know what the first day of a year is? Type in a year and use the guide below to understand what the number you typed in means!
<input id="inputYear" placeholder="Input a Year">
<button onclick="firstDayOfYear(getYear())">Submit</button>
<p id="theFirstDayOfYear"></p>