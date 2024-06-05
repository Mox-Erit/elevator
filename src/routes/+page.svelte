<!-- 
    Elevator Project

    @Author: Chase
    NOTE: In the UK, the street level is called 'Ground floor' and for the US it is often referred to as the '1st Floor'. We will be using 'Ground floor' as a default to avoid confusion.

    Notes:
    - Keep track when door is traveling or set timers for when functions are called.

    Requirements:
    - Must be able to call the elevator to a floor
    - Animate the elevator whenever called to a new floor
    - Animate the doors opening and simulate time for passengers to embark / disembark
    - 508 accessibility for buttons

    Additional features:
    - Fire department button
    - Hold door open or close door
    - Elevator music

    If given more time:
    - Test cases for asserting button reaches position on page, emergency is called, and doors are open / closed.
    - Set up a queue to manage multiple requests
 -->

 <script>

function emergencyServices() {
    alert("Chase has been called!");
}
function groundFloor() {
    // Call the closedoors() function
    closeDoors();
    
    // Scroll to the bottom of the page smoothly
    setTimeout (() => window.scrollTo({ top: 6000, left: 0, behavior: 'smooth' }), 1000); // window.scrollTo({ top: 10000, left: 0, behavior: 'smooth' });

    // Call the openDoors() function
    setTimeout(() => openDoors(), 2000); // openDoors();
}
function firstFloor() {
    // Call the closedoors() function
    closeDoors();
    
    // Scroll to the bottom of the page smoothly
    setTimeout (() => window.scrollTo({ top: 3600, left: 0, behavior: 'smooth' }), 1000); // window.scrollTo({ top: 10000, left: 0, behavior: 'smooth' });

    // Call the openDoors() function
    setTimeout(() => openDoors(), 2000); // openDoors();
}
function secondFloor() {
    // Call the closedoors() function
    closeDoors();
    
    // Scroll to the bottom of the page smoothly
    setTimeout (() => window.scrollTo({ top: 2100, left: 0, behavior: 'smooth' }), 1000); // window.scrollTo({ top: 10000, left: 0, behavior: 'smooth' });

    // Call the openDoors() function
    setTimeout(() => openDoors(), 2000); // openDoors();
}

function thirdFloor() {
    // Call the closedoors() function
    closeDoors();
    
    // Scroll to the bottom of the page smoothly
    setTimeout (() => window.scrollTo({ top: 600, left: 0, behavior: 'smooth' }), 1000); // window.scrollTo({ top: 10000, left: 0, behavior: 'smooth' });

    // Call the openDoors() function
    setTimeout(() => openDoors(), 2000); // openDoors();
}


function closeDoors() {
  // close the doors
  let doorElement = document.querySelector('.door');

  // Toggle between two different widths (e.g., 100px and 200px)
  doorElement.style.width = '70vw';
}
function openDoors() {
  // check if we are moving function?

  let doorElement = document.querySelector('.door');

  // Toggle between two different widths (e.g., 100px and 200px)
  doorElement.style.width = '15vw';
}
 </script>
 <div class="page">
    <div class="container">
        <div class="btns">
            <div class="btn-wrapper bottom"><button on:click={groundFloor} aria-label="Go to ground floor" class="btn">G</button></div>
            <div class="btn-wrapper floor"><button  on:click={firstFloor} aria-label="Go to the first floor" class="btn floor">1</button></div>
            <div class="btn-wrapper floor"><button  on:click={secondFloor} aria-label="Go to the second floor" class="btn floor">2</button></div>
            <div class="btn-wrapper floor"><button  on:click={thirdFloor} aria-label="Go to the third floor" class="btn floor">3</button></div>
            <div class="btn-wrapper floor"><button on:click={emergencyServices} aria-label="Call emergency services" class="btn floor">!</button></div>
            <div class="btn-wrapper floor"><button  on:click={openDoors} aria-label="Go to open the doors" class="btn floor">Open</button></div>
            <div class="btn-wrapper floor"><button  on:click={closeDoors} aria-label="Go to close the doors" class="btn floor">Close</button></div>
        </div>
    </div>
    <div class="door">

    </div>
    <div class="indicator">
        <div class="level"></div>
        <div class="level"></div>
        <div class="level"></div>
        <div class="level"></div>
    </div>
 </div>
 



<style>
    .page {
        height: 6000px;
        display: flex;
        flex-direction: row;
    }
    .container {
        background-color: blue;
        width: 25vw;
        height: 100vh;
       position: fixed;
    }
    .indicator {
        position: fixed;
        width: 5vw;
        display: flex;
        flex-direction: column;
        height: 100vh;
        background-color: orange;
        left: 95vw;
    }
    .level {
        width: 100%;
        height: 25%;
        border-top: 80px solid black;
    }
    .level:not(:last-child) {
        width: 100%;
        height: 25%;
        border-top: 85px solid black;
    }
    .door {
        position: fixed;
        left: 25vw;
        background-color: grey;
        height: 100vh;
        width: 70vw;
        content: '';
        transition: all 0.5s ease-in-out;
    }
    .doorOpen {
        transform: translatex(200px);
    }

</style>