
<script>
    const logoUrl = new URL('../public/logo.png', import.meta.url).href
    const formUrl = 'https://docs.google.com/forms/d/e/1FAIpQLSe1oLrxaNzDOSdHQ9fDgNUWj3rTf5L0PKQl7suxVs-D1YlJQQ/viewform'
</script>

<body>
    <div class="navbar">
        <div class="logo">
            <img src="{logoUrl}" alt="Logo" />
        </div>
        <div class="buttons">
            <button class="button"><h2>Home</h2></button>
            <a href="{formUrl}" target="_blank" class="button"><h2>Get In Touch</h2></a>
        </div>
    </div>
</body>

<style>
    @import url('https://fonts.googleapis.com/css2?family=Outfit&display=swap');
        
    body {
        background-color: black;
        color: white;
        margin: 0;
        padding: 0;
    }

    .navbar {
        display: flex;
        justify-content: space-between;
        align-items: center;
        padding: 20px;
    }

    .logo img {
        max-width: 120px;
        height: auto;
    }

    .buttons {
        display: flex;
        gap: 10px;
        
    }

    .button {
        display: inline-block;
        border: none;
        padding: 0px 20px;
        background-color: transparent;
        color: white;
        cursor: pointer;
        min-width: 150px;
        position: relative; 
        overflow: hidden; 
        text-decoration: none;
        font-size: 15px;
    }

    /* .button:hover {
        border-bottom: 2px solid #14C9B4;
    } */

    .button::after {
        content: "";
        position: absolute;
        bottom: 0;
        left: 50%; /* Position the border at the center initially */
        transform: translateX(-50%); /* Center the border horizontally */
        width: 0;
        height: 2px;
        background-color: #14C9B4;
        transition: width 0.3s ease-in-out; /* Apply a transition for the width property */
    }

    .button:hover::after {
        width: 100%; /* Expand the width to make the border appear */
    }

    h2 {
        font-family: Outfit;
    }


</style>
