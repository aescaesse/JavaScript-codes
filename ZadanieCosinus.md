### Polecenie
```
1.Stwórz stronę zawierającą skrypt wyświetlający 10 razy słowo: cosinus

2.Zmodyfikuj poprzedni skrypt w ten sposób, że użytkownik zdecyduje o liczbie wyświetleń słowa cosinus

3.Użytkownik podaje dwie liczby całkowite, nazwijmy je a i b, przy czym a jest mniejsze od b. Wyświetl wszyskie liczby całkowite zawarte pomiędzy a i b,

4.Zmodyfikuj poprzedni skrypt w ten sposób, że będzie on działa dla dowolnych liczb całkowitych podanych przez użytkownika 
(czyli także w przypadkach gdy a jestrówne b oraz gdy a jest większe od b.

5.W udostępnionym folderze znajduje się 9 obrazków zapisanych w plikach o nazwach
tlo11.gif ÷ tlo19.gif – wyświetl wszystkie z użyciem pętli.

6.Wyświetl liczby pierwsze zawarte w przedziale od minimum do maksimum podanego
przez użytkownika. 
```
<img src="Zdjecia/cosinus.png" width=400 height=150>
``` html javascript
<!DOCTYPE html>
<html lang="pl">
<head>
    <meta charset="UTF-8">
	<title> Cosinus </title>
    <script>
	  window.onload = function Cwiczenie5i1() {
	
            var cos = "cosinus";
            for (var i = 1; i <= 10; i++)
                document.getElementById("cosinusCw1").innerHTML += cos + "<br / > ";
				
            var obrazki = ["tlo11.gif", "tlo12.gif", "tlo13.gif","tlo14.gif", "tlo15.gif", "tlo16.gif", "tlo17.gif", "tlo18.gif", "tlo18.gif"];
            for (var i = 0; i < 9; i++)
                document.getElementById("ObrazkiCw5").innerHTML += '<img width = 100 height = 100 src = "'+obrazki[i]+'" /> ';
        }
		
        function Cwiczenie2() {
		
            var ile = document.getElementById("ileCosinusow").value;
            var cosinus = "cosinus";
            var cosOutput = "";
            for (var i = 1; i <= ile; i++)
                cosOutput += cosinus + "<br />";
            document.getElementById("cosinusCw2").innerHTML = cosOutput;
        }

        function Cwiczenie3() {
		
            var x = parseInt(document.getElementById("Liczba1").value);
            var y = parseInt(document.getElementById("Liczba2").value);
            var LiczbaOutput = "";
            if (x < y) {
                for (var i = x + 1; i < y; i++)
                    LiczbaOutput += i + " ";
                document.getElementById("LiczbyCw3").innerHTML = LiczbaOutput;
            } else document.getElementById("LiczbyCw3").innerHTML = "Pierwsza liczba musi być mniejsza!";
        }

        function Cwiczenie4() {
		
            var x = parseInt(document.getElementById("Liczba1Cw4").value);
            var y = parseInt(document.getElementById("Liczba2Cw4").value);
            var IleLiczb = x - y;
            IleLiczb = Math.abs(IleLiczb);
            var LiczbaOutput = "";
            if (x < y)
                for (var i = x + 1; i <= IleLiczb; i++)
                    LiczbaOutput += i + " ";
            else
                for (var i = y + 1; i <= IleLiczb; i++)
                    LiczbaOutput += i + " ";
            document.getElementById("LiczbyCw4").innerHTML = LiczbaOutput;
        }

        function Cwiczenie6() {
		
            function CzyPierwsza(n) {
                if (n == 2) return 1;
                else if (n <= 1 || n % 2 == 0) return 0;
                else
                    for (var i = 3; i < n; i++)
                        if (n % i == 0)
                            return 0;
                return 1;
            }
            var LiczbaOutput = "";
            var x = parseInt(document.getElementById("Liczba1Cw6").value);
            var y = parseInt(document.getElementById("Liczba2Cw6").value);
            var IleLiczb = x - y;
            IleLiczb = Math.abs(IleLiczb);
            if (x < y) {
                for (var i = x + 1; i <= IleLiczb + 1; i++)
                    if (CzyPierwsza(i) == 1)
                        LiczbaOutput += i + " ";
            } else {
                for (var i = y + 1; i <= IleLiczb + 1; i++)
                    if (CzyPierwsza(i) == 1)
                        LiczbaOutput += i + " ";
            }
            document.getElementById("LiczbyCw6").innerHTML = LiczbaOutput;
        }
    </script>
	<style>
    body {
        background-color: rgba(25, 24, 24, 0.89);
    }
    
    * {
        margin: 0;
        padding: 0;
    }
    
    .kontener {
        margin: auto;
        width: 70%;
        margin-top:2%;
    }
    
    .cwiczenie {
        padding: 10px;
        background-color: rgba(2, 2, 2, 0.3);
        border-radius: 20px;
        color: white;
        margin-top: 5px;
    }
    
    .naglowek {
        text-align: center;
        letter-spacing: 5px;
        font-family: Courier;
        padding: 5px;
    }
    
    .form {
        margin-left: 10%;
        padding: 5px;
    }
    
    output {
        padding: 2px;
        font-size: 20px;
    }
    
    input {
        border: none;
        background-color: rgba(25, 24, 24, 0.89);
        width: 200px;
        height: 30px;
        text-align: center;
        color: white;
    }
    
    button {
        border: none;
        background-color: rgba(25, 24, 24, 0.89);
        width: 70px;
        height: 30px;
        text-align: center;
        color: white;
        color: grey;
    }
</style>

</head>
<body>
    <div class="kontener">
        <section class="cwiczenie">
            <h1 class="naglowek">Ćwiczenie 1</h1>
            <div class="input">
                <form class="form">
                    <output id="cosinusCw1"></output>
                </form>
            </div>
        </section>
        <section class="cwiczenie">
            <h1 class="naglowek">Ćwiczenie 2</h1>
            <div class="input">
                <form class="form">
                    <input id="ileCosinusow" placeholder="Wpisz liczbę"> 
                    <button type="button" onClick="Cwiczenie2();">Wyświetl</button>
                    <br />
                    <output id="cosinusCw2"></output>
                </form>
            </div>
        </section>
        <section class="cwiczenie">
            <h1 class="naglowek">Ćwiczenie 3</h1>
            <div class="input">
                <form class="form">
                    <input id="Liczba1" placeholder="Wpisz liczbę"> 
                    <input id="Liczba2" placeholder="Wpisz liczbę"> 
                    <button type="button" onClick="Cwiczenie3();">Wyświetl</button>
                    <br />
                    <output id="LiczbyCw3"></output>
                </form>
            </div>
        </section>
        <section class="cwiczenie">
            <h1 class="naglowek">Ćwiczenie 4</h1>
            <div class="input">
                <form class="form">
                    <input id="Liczba1Cw4" placeholder="Wpisz liczbę"> 
                    <input id="Liczba2Cw4" placeholder="Wpisz liczbę"> 
                    <button type="button" onClick="Cwiczenie4();">Wyświetl</button>
                    <br />
                    <output id="LiczbyCw4"></output>
                </form>
            </div>
        </section>
        <section class="cwiczenie">
            <h1 class="naglowek">Ćwiczenie 5</h1>
            <div class="input">
                <form class="form">
                    <output id="ObrazkiCw5"></output>
                </form>
            </div>
        </section>
        <section class="cwiczenie">
            <h1 class="naglowek">Ćwiczenie 6</h1>
            <div class="input">
                <form class="form">
                    <input id="Liczba1Cw6" placeholder="Wpisz liczbę"> 
                    <input id="Liczba2Cw6" placeholder="Wpisz liczbę"> 
                    <button type="button" onClick="Cwiczenie6();">Wyświetl</button>
                    <br />
                    <output id="LiczbyCw6"></output>
                </form>
            </div>
        </section>
    </div>
</body>
</html>

```