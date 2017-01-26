<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <title>Document</title>
    <link rel="stylesheet" href="css/reset.css">
    <link rel="stylesheet" type="text/css" href="js/pickadate.js-master/lib/themes/default.css">
    <link rel="stylesheet" type="text/css" href="js/pickadate.js-master/lib/themes/default.date.css">
    <link rel="stylesheet" href="js/timedropper-master/timedropper.min.css">
    <link rel="stylesheet" type="text/css" href="css/style.css">
    <script src="js/jquery-2.2.4.min.js"></script>
    <script src="js/pickadate.js-master/lib/picker.js"></script>
    <script src="js/pickadate.js-master/lib/picker.date.js"></script>
    <script src="js/jquery-validation-master/src/core.js"></script>
    <script src="js/jquery-validation-master/src/additional/accept.js"></script>
    <script src="js/timedropper-master/timedropper.js"></script>
    <script src="js/main.js"></script>
</head>

<body>
    <div id="container">
        <h1>Vraag je persoonlijke offerte aan</h1>
        	<?php
        if(isset($_GET['error']) && $_GET['error'] == 0){
            echo '<p class="warning">Gelieve het formulier in te vullen.</p>';	
        }
        if(isset($_GET['error']) && $_GET['error'] == 1){
            echo '<p class="warning">Undefined error</p>';	
        }
        if(isset($_GET['error']) && $_GET['error'] == 2){
            echo '<p class="warning">De bijlage PLAATEGROND is geen geldig PDF-bestand</p>';	
        }	
        if(isset($_GET['error']) && $_GET['error'] == 3){
            echo '<p class="warning">De bijlage PLATTEGROND is geen PDF-bestand</p>';	
        }	
        if(isset($_GET['error']) && $_GET['error'] == 4){
            echo '<p class="warning">De bijlage PLAATTEGROND is te groot (max 2MB)</p>';	
        }	
        if(isset($_GET['error']) && $_GET['error'] == 5){
            echo '<p class="warning">De bijlage AFFICHE is geen geldig PDF-bestand</p>';	
        }
        if(isset($_GET['error']) && $_GET['error'] == 6){
            echo '<p class="warning">De bijlage AFFICHE is geen PDF-bestand</p>';	
        }		
        if(isset($_GET['error']) && $_GET['error'] == 7){
            echo '<p class="warning">De bijlage AFFICHE is te groot (max 2MB)</p>';	
        }		
        if(isset($_GET['error']) && $_GET['error'] == 8){
            echo '<p class="warning">Voornaam werd niet ingevuld</p>';	
        }
        if(isset($_GET['error']) && $_GET['error'] == 9){
            echo '<p class="warning">Achternaam werd niet ingevuld</p>';	
        }	
        if(isset($_GET['error']) && $_GET['error'] == 10){
            echo '<p class="warning">Bedrijf werd niet ingevuld</p>';	
        }		
        if(isset($_GET['error']) && $_GET['error'] == 11){
            echo '<p class="warning">E-mail werd niet ingevuld</p>';	
        }
        if(isset($_GET['error']) && $_GET['error'] == 12){
            echo '<p class="warning">Straat werd niet ingevuld</p>';	
        }		
        if(isset($_GET['error']) && $_GET['error'] == 13){
            echo '<p class="warning">Huisnummer werd niet ingevuld</p>';	
        }		
        if(isset($_GET['error']) && $_GET['error'] == 14){
            echo '<p class="warning">Postcode werd niet ingevuld</p>';	
        }		
        if(isset($_GET['error']) && $_GET['error'] == 15){
            echo '<p class="warning">Gemeente werd niet ingevuld</p>';	
        }		
        if(isset($_GET['error']) && $_GET['error'] == 16){
            echo '<p class="warning">Eventnaam werd niet ingevuld</p>';	
        }		
        if(isset($_GET['error']) && $_GET['error'] == 17){
            echo '<p class="warning">Datum werd niet ingevuld</p>';	
        }		
        if(isset($_GET['error']) && $_GET['error'] == 18){
            echo '<p class="warning">Begin-uur werd niet ingevuld</p>';	
        }		
        if(isset($_GET['error']) && $_GET['error'] == 19){
            echo '<p class="warning">Eind-uur werd niet ingevuld</p>';	
        }		
        if(isset($_GET['error']) && $_GET['error'] == 20){
            echo '<p class="warning">Het bestand PLATTEGROND werd niet geselecteerd</p>';	
        }		
    ?>	    
        <form action="send.php" enctype="multipart/form-data" method="post" id="formulier">

            <div class="gegevenstype">
                <h2>Organisator</h2>
                <div class="formElement">
                    <label for="voornaam">Voornaam:</label>
                    <input type="text" name="voornaam">
                </div>
                <div class="formElement">
                    <label for="">Achternaam:</label>
                    <input type="text" name="achternaam">
                </div>
                <div class="formElement">
                    <label for="bedrijf">Bedrijf / Organisatie:</label>
                    <input type="text" name="bedrijf">
                </div>
                <div class="formElement">
                    <label for="email">E-mail:</label>
                    <input type="text" name="email">
                </div>
            </div>

            <div class="gegevenstype">
                <h2>Locatie</h2>
                <div class="formElement">
                    <label for="">Straat:</label>
                    <input type="text" name="straat">
                </div>
                <div class="formElement">
                    <label for="">Nummer:</label>
                    <input type="number" min="1" name="huisnummer">
                </div>
                <div class="formElement">
                    <label for="bus">Bus:</label>
                    <input type="text" name="bus">
                </div>
                <div class="formElement">
                    <label for="">Postcode:</label>
                    <input type="number" min="1000" max="9999" name="postcode">
                </div>
                <div class="formElement">
                    <label for="">Gemeente:</label>
                    <input type="text" name="gemeente">
                </div>
                <div class="formElement">
                    <label for="kaart">Plattegrond:</label>
                    <input type="file" name="kaart">
                </div>
            </div>

            <div class="gegevenstype">
                <h2>Event</h2>
                <div class="formElement">
                    <label for="">Benaming:</label>
                    <input type="text" name="eventnaam">
                </div>
                <div class="formElement">
                    <label for="">Datum:</label>
                    <input type="text" name="datum" class="datepicker">
                </div>
                <div class="formElement">
                    <label for="">Begin-uur:</label>
                    <input type="text" name="begin" class="alarm">
                </div>
                <div class="formElement">
                    <label for="">Eind-uur:</label>
                    <input type="text" name="einde" class="alarm">
                </div>
                <div class="formElement">
                    <label for="affiche">Affiche:</label>
                    <input type="file" name="affiche">
                </div>
            </div>
            <input type="submit" name="knop" value="Vraag aan">
        </form>
    </div>
</body>

</html>
