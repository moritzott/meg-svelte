<script>
    import { createEventDispatcher } from "svelte";
    const dispatch = createEventDispatcher();

    let mail = {
        absenderName: "",
        empfaengerGeschlecht: "Sehr geehrte Damen und Herren der",
        empfaengerName: "",
        mailText: "",
        grussformel: "Mit freundlichen Grüßen"
    };

    const createMailDraft = (event) => {

        event.preventDefault();
   
        // create Mail and send one level up to component
        dispatch("create-mail-from-input", mail);

        // reset the mail form:
        mail = {
            absenderName: "",
            empfaengerGeschlecht: "Sehr geehrte Damen und Herren der",
            empfaengerName: "",
            mailText: "",
            grussformel: "Mit freundlichen Grüßen"
        };
    };



</script>

<form action="#" method="post">
    <div>
        <label for="absenderName">Ihr Name:</label>
        <input bind:value="{mail.absenderName}" class="form-control" type="text" name="absenderName" id="absenderName" required>
    </div>
    <div>
        <label for="empfaengerGeschlecht">Empfänger:</label>
        <select bind:value="{mail.empfaengerGeschlecht}" name="empfaengerGeschlecht" id="empfaengerGeschlecht">
            <option value="Sehr geehrte Damen und Herren der" selected >Organisation/Behörde</option>
            <option value="Sehr geehrter Herr">Mann</option>
            <option value="Sehr geehrte Frau">Frau</option>   
        </select>
    </div>
    <div>
        <label for="empfaengerName">Name des Empfängers (bei Personen nur Nachname):</label>
        <input bind:value="{mail.empfaengerName}" type="text" name="empfaengerName" id="empfaengerName" required>
    </div>
    <div>
        <label for="mailText" >Text (mit kleinem Buchstaben beginnen):</label>
        <textarea bind:value="{mail.mailText}" lang="de" name="mailText" id="mailText" rows="10"></textarea>
    </div>
    <div>
        <label for="grussformel">Grußformel:</label>
        <select bind:value="{mail.grussformel}" name="grussformel" id="grussformel">
            <option value="Mit freundlichen Grüßen">Mit freundlichen Grüßen</option>
            <option value="Hochachtungsvoll">Hochachtungsvoll</option>
            <option value="Beste Grüße">Beste Grüße</option>
            <option value="Mit besten Grüßen">Mit besten Grüßen</option>
            <option value="Liebe Grüße">Liebe Grüße</option>
            <option value="Herzliche Grüße">Herzliche Grüße</option>
            <option value="Viele Grüße">Viele Grüße</option>
        </select>
    </div>
    <div class="center">
        <input on:click="{createMailDraft}" type="submit" value="Erzeuge Mail-Entwurf">
    </div>
</form>

<style>

    form {
        padding: 10px;
    }

    div {
        padding: 12px;
    }

    label {
        display: block;
        width: 90%;
        margin: auto;
        line-height: 1.5;
        margin-bottom: 8px;
    }



    select, textarea, input[type="text"] {
        background-color: white;
        margin: auto;
        display:block;
        width: 90%;
        border: 1px solid #ced4da;
        border-radius: 3px;
        line-height: 1.5;
        height: 30px;
        font-size: medium;
    }

    select:focus, textarea:focus, input[type="text"]:focus {
        color: #212529;
        background-color: #fff;
        border-color: #86b7fe;
        outline: 0;
        box-shadow: 0 0 0 0.25rem rgba(13, 110, 253, 0.25);
    }

    input[type="text"] {
        height: 31px;
        padding-left: 5px;
    }

    select {
        height: 36px;
        font-size: medium;
        width: 93%;
    }

    textarea {
        height: 250px;
        font-family: inherit;
        font-size: inherit;
        padding-left: 5px;
    }

    .center {
        text-align: center;
    }

    input[type="submit"] {
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

    input[type="submit"]:hover {

        background-color: #0b5ed7;
        border-color: #0a58ca;

    }


</style>