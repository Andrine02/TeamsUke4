# TeamsUke4
Team Oppgave Uke 4
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <div id="app"></div>

    
    <script>

        const app = document.getElementById('app');
        let outputterBamse = "";
        let outputterHus = "";
        let outputter3 = "";
        let selectedBamse = ["selected", "", "", "", ""];
        let selectedHus = ["selected", "", "", "", ""];

        viewer();
        function viewer(){
            app.innerHTML = /*HTML*/`
            <div class="text"> 
                Det var en gang en hvit bamse med
                <select class="select" onchange="bamse(this)">
                    <option ${selectedBamse[0]} value=0>Velg bamse</option>
                    <option ${selectedBamse[1]} value=1>Rød</option>
                    <option ${selectedBamse[2]} value=2>Blå</option>
                    <option ${selectedBamse[3]} value=3>Grønn</option>
                    <option ${selectedBamse[4]} value=4>Rosa</option>
                </select>
                farger. Han bodde i et
                <select class="select" onchange="hus(this)">
                    <option ${selectedHus[0]} value=0>Velg hus</option>
                    <option ${selectedHus[1]} value=1>Rød</option>
                    <option ${selectedHus[2]} value=2>Blå</option>
                    <option ${selectedHus[3]} value=3>Grønn</option>
                    <option ${selectedHus[4]} value=4>Rosa</option>
                </select>
                hus.
                <div>
                    <img class="bamse"src="${outputterBamse}" alt="">
                    <img class="hus" src="${outputterHus}" alt="">
                </div>
            </div>`;
        }


        function bamse(imgPath){
           
            let fromIndex = selectedBamse.indexOf('selected');
            let toIndex = imgPath.value;
            let element = selectedBamse.splice(fromIndex, 1)[0];
            selectedBamse.splice(toIndex, 0, element);
            
            if(imgPath.value != 0) {
                outputterBamse = "/img/bamse/" + imgPath.value + '.png';
            }else {
                outputterBamse = "";
            }
            
            viewer();
        }

        function hus(imgPath){
           
           let fromIndex = selectedHus.indexOf('selected');
           let toIndex = imgPath.value;
           let element = selectedHus.splice(fromIndex, 1)[0];
           selectedHus.splice(toIndex, 0, element);
           
           if(imgPath.value != 0) {
               outputterHus = "/img/hus/" + imgPath.value + '.png';
           }else {
               outputterHus = "";
           }
           
           viewer();
        }
        function CreateBamseSelect() {

        }
        function ordklikker(x){
            outputter2 = x.innerHTML;
            viewer();
        }
    </script>
</body>
</html>

