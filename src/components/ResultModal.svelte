<script>
    import { createEventDispatcher } from "svelte";
    const dispatch = createEventDispatcher();

    // Mail-Objekt von übergeordneter Komponente bekommen:
    export let mail;

    // Mail-Standard-Formatierung:
    const mailFormat = `${mail.empfaengerGeschlecht} ${mail.empfaengerName},\n\n${mail.mailText}\n\n${mail.grussformel}\n${mail.absenderName}`;

    // gebunden an das Textausgabefeld: Nachträgliche Mailänderungen können über
    // output.value in die Zwischenablage kopiert werden
    let output;

    const copyTextToClipboard = () => {
        // nicht über mailFormat-Variable -> weil ggf. im Textfeld noch Änderungen
        // vom Nutzer nachträglich gemacht werden => output.value ist aktueller Zustand!
        navigator.clipboard.writeText(output.value)
            .then(() => {
                console.log("Text copied to clipboard");
            })
            .catch((err) => {
                console.log(`An error occured : ${err}`);
            })
    };

</script>

<!-- the modal -->
<div class="modal" >
    
    <!-- modal content -->
    <div class="modal-content">

        <!-- header -->
        <div class="modal-header">
            <button class="topCloseBtn" on:click={ () => { dispatch("close-restult-modal"); } }  >&times;</button>
            <h2>Ihre Mail</h2>
        </div>

        <!-- body -->
        <div class="modal-body">
            <!-- gebe die formatierte Mail (mailFormat) in einem Textarea-Feld aus -->
            <textarea bind:this={output} value={mailFormat} lang="de" cols="1" rows="10"></textarea>
        </div>

        <div class="footer">
            <div class="button-group">
                <button on:click={ () => { dispatch("close-restult-modal"); } } class="closeBtn">Schließen</button>
                <button on:click={copyTextToClipboard} class="copyTextBtn">Kopiere Text</button>
            </div>  
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

    }

    .modal-content {
        border-radius: 10px;
        background-color: white;
        position: relative;
        max-width: 70%;
        
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

    }


    .topCloseBtn {
        float: right;
        cursor: pointer;
        border: none;
        background-color: white;
        font-size: 2em;
    }



    /* .center {
        text-align: center;
    } */

    h2 {
        margin-bottom: 5px;
    }

    /* .footer {
        text-align: center;
    } */

    /* .copyTextBtn {
        margin-left: 20px;
    }

    .closeBtn {
        margin-right: 20px;
    } */



    .copyTextBtn, .closeBtn {
        margin-bottom: 20px;
    }

    .closeBtn {
        color: #fff;
        background-color: #6c757d;
        border-color: #6c757d;
        border-radius: 3px;
        border: 1px solid transparent;
        cursor: pointer;
        font-size: medium;
        padding: 10px;
        /* height: 35px; */
        margin-right: 3px;
    }

    .closeBtn:hover {

        background-color: #5c636a;
        border-color: #565e64;

    }

    .copyTextBtn {
        color: #fff;
        background-color: #0d6efd;
        border-color: #0d6efd;
        border-radius: 3px;
        border: 1px solid transparent;
        cursor: pointer;
        font-size: medium;
        /* height: 35px; */
        padding: 10px;
    }

    .copyTextBtn:hover {

        background-color: #0b5ed7;
        border-color: #0a58ca;

    }

    .button-group {
        text-align: right;
        margin-right: 15px;
        
    }


    textarea {
        background-color: white;
        margin: auto;
        padding: 10px;
        display:block;
        width: 90%;
        border: 1px solid #ced4da;
        border-radius: 3px;
        line-height: 1.5;
        height: 30px;
        font-size: medium;
        height: 250px;
        font-family: inherit;
        font-size: inherit;
        margin-top: 20px;
        margin-bottom: 20px;
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

        .modal-body {
            padding-left: 10px;
            padding-right: 10px;
        }

        textarea {
            width: 90%;
            /* margin-left: 4px;
            margin-right: 4px; */
        }
    }


</style>