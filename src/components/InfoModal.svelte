<script>
    import { createEventDispatcher } from "svelte";
    const dispatch = createEventDispatcher();
</script>

<!-- the modal -->
<div class="modal" >
    
    <!-- modal content -->
    <div class="modal-content">

        <!-- header -->
        <div class="modal-header">
            <button class="topCloseBtn" on:click="{ () => { dispatch("close-info-modal"); } }" >&times;</button>
            <h2>Informationen</h2>
        </div>

        <!-- body -->
        <div class="modal-body">
            <h3>Beschreibung</h3>
            <p>
                Manchmal muss man Mails über das Smartphone schreiben.
                Gegenüber einem PC hat dabei man den Nachteil, dass man sich öfter
                vertippt und das Schreiben auf dem kleinen Touchscreen
                unangenehm ist.
            </p>
            <p>
                Der <em>MEG</em> ist ein Mail-Entwurfs-Generator, der 
                gewöhnliche Begrüßungs- und Schlussfloskeln setzt, Absendername und Empfänger aufnimmt und die
                Mail entsprechend mit Abständen automatisiert formatiert.
                Man schreibt auf diese Weise hübschere und korrektere Mails
                in schnellerer Geschwindigkeit. Man muss sich auch weniger
                Gedanken um Schreibfehler machen.
            </p>
            <h3>Kontakt</h3>
            <p>Wenn Sie Fragen haben oder Erweiterungen vorschlagen möchten:</p>
            <div class="center">
                <img src="img/contactMail.png" alt="contactMailAddress" width="250px;">
            </div>
            <h3>Benutzte Komponenten</h3>
            <p>
                Für die Icons wurde die Schriftart <em>Roboto</em> verwendet, deswegen
                muss ich hier eine entsprechende Information kundtun:
            </p>
            <p>Name der benutzen Komponente: Roboto</p>
            <p>Lizenzgeber: Google Inc.</p>
            <p>Lizenz: <a href="https://www.apache.org/licenses/LICENSE-2.0.html" target="_blank">Apache License v2.0</a></p>
            <h3>Version</h3>
            <p>
                Die aktuelle Version ist 2.0.0.
            </p>
            <br>
            <!-- <div class="center">
                <button class="closeBtn" on:click="{ () => { dispatch("close-info-modal"); } }" >Schließen</button>
            </div> -->
            
            

        </div>

        

    </div>


</div>



<style>
    .modal {
        padding-top: 40px; /* Location of the box */
        z-index: 1; /* Show on top always */
        position: fixed; /* Stay in place */
        left: 0;
        top: 0;
        width: 100%; /* Full width */
        height: 100%; /* Full height */
        overflow: auto; /* Enable scroll if needed */
        background-color: rgba(0,0,0,0.4); /* Black w/ opacity */
        padding-bottom: 10px;

    }



    .modal-content {
        border-radius: 10px;
        background-color: white;
        position: relative;
        overflow: auto;
        /* width: 90%; */
        max-width: 70%;
        height: 90%;
        margin-left: auto;
        margin-right: auto;
        margin-bottom: 20px;

    }

    .modal-header {
        padding-left: 30px;
        padding-top: 7px;
        padding-right: 8px;
        border-bottom: solid lightgray 1px;

    }

    .modal-body {
        padding-left: 30px;
        padding-right: 30px;
        padding-top: 5px;
        padding-bottom: 20px;
        /* border-bottom: solid lightgray 1px; */

    }


    .topCloseBtn {
        float: right;
        cursor: pointer;
        border: none;
        background-color: white;
        font-size: 2em;
    }



    .center {
        text-align: center;
    }

/* 
    .closeBtn {
        color: #fff;
        background-color: #6c757d;
        border-color: #6c757d;
        border-radius: 3px;
        border: 1px solid transparent;
        cursor: pointer;
        font-size: medium;
        padding: 10px;
    }

    .closeBtn:hover {

        background-color: #5c636a;
        border-color: #565e64;

    } */


    h2 {
        margin-bottom: 5px;
    }

    @media screen and (max-width: 599px){
        .modal-content {
            max-width: 80%;
        }
        
    }
    
    @media screen and (max-width: 400px){
        .modal-content {
            max-width: 95%;
        }

        /* .modal-body {
            padding-left: 10px;
            padding-right: 10px;
        } */

    }

</style>