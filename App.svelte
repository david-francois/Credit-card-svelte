<script>
import Form from "./components/Form.svelte";
import Card from "./components/Card.svelte";
</script>

<div class="container">
  <Card/>
  <Form/>
</div>

<style>
  @import url("https://fonts.googleapis.com/css2?family=Poppins:wght@100;200;300;400;500;600&display=swap");

  * {
    font-family: "Poppins", sans-serif;
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    outline: none;
    border: none;
    text-decoration: none;
    text-transform: uppercase;
  }

  .container {
    min-height: 98vh;
    background: #eee;
    display: flex;
    align-items: center;
    justify-content: center;
    flex-flow: column;
    padding-bottom: 60px;
  }
</style>

