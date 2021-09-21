<script>
  import {
    cardNumber,
    cardHolder,
    selectedMonth,
    selectedYear,
    ccv
  } from "../store/Store.js";
</script>

<script context="module">
  export function ccvEnter() {
    document.querySelector(".front").style.transform =
      "perspective(1000px) rotateY(-180deg)";
    document.querySelector(".back").style.transform =
      "perspective(1000px) rotateY(0deg)";
  }

  export function ccvLeave() {
    document.querySelector(".front").style.transform =
      "perspective(1000px) rotateY(0deg)";
    document.querySelector(".back").style.transform =
      "perspective(1000px) rotateY(180deg)";
  }
</script>

<div class="card-container">
	<div class="front">
		<div class="image">
			<h1>Visa</h1>     
		</div>
		<div class="card-number-box">{$cardNumber}</div>
		<div class="flexbox">
			<div class="box">
				<span>card holder</span>
				<div class="card-holder-name">{$cardHolder}</div>
			</div>
			<div class="box">
				<span>expires</span>
				<div class="expiration">
					<span class="exp-month">{$selectedMonth}</span>
					<span class="exp-year">{$selectedYear}</span>
				</div>
			</div>
		</div>
	</div>
	<div class="back">
		<div class="stripe">
			<div class="box">
				<span>ccv</span>
				<div class="ccv-box">{$ccv}</div>
				<img src="../images/visa.png" alt="">
			</div>
		</div>
	</div>
</div>

<style>
  .card-container {
    margin-bottom: -100px;
    position: relative;
    height: 230px;
    width: 400px;
  }

  .card-container .front {
    position: absolute;
    height: 100%;
    width: 100%;
    top: 0;
    left: -20px;
    background: linear-gradient(45deg, blueviolet, deeppink);
    border-radius: 5px;
    backface-visibility: hidden;
    box-shadow: 0 15px 25px rgba(0, 0, 0, 0.2);
    padding: 20px;
    transform: perspective(1000px) rotateY(0deg);
    transition: transform 0.4s ease-out;
  }

  .card-container .front .image {
    display: flex;
    align-items: center;
    justify-content: flex-end;
  }

  .card-container .front .image h1 {
    font-size: 32px;
    color: #fff;
    margin-top: 5px;
  }

  .card-container .front .card-number-box {
    padding: 30px 0;
    font-size: 22px;
    color: #fff;
  }

  .card-container .front .flexbox {
    display: flex;
  }

  .card-container .front .flexbox .box:nth-child(1) {
    margin-right: auto;
  }

  .card-container .front .flexbox .box {
    font-size: 15px;
    color: #fff;
  }

  .card-container .back {
    position: absolute;
    top: 0;
    left: -20px;
    height: 100%;
    width: 110%;
    background: linear-gradient(45deg, blueviolet, deeppink);
    border-radius: 5px;
    padding: 20px 0;
    text-align: right;
    backface-visibility: hidden;
    box-shadow: 0 15px 25px rgba(0, 0, 0, 0.2);
    transform: perspective(1000px) rotateY(180deg);
    transition: transform 0.4s ease-out;
  }

  .card-container .back .stripe {
    background: #000;
    width: 100%;
    margin: 20px 0;
    height: 50px;
  }

  .card-container .back .box {
    padding: 0 20px;
  }

  .back .box span {
    color: #000;
    font-size: 15px;
  }

  .ccv-box {
    height: 50px;
    padding: 10px;
    margin-top: 80px;
    color: #333;
    background: #fff;
    border-radius: 5px;
    width: 95%;
    display: flex;
    justify-content: flex-end;
    align-items: center;
  }

  .card-container .back .box img {
    margin-top: 30px;
    height: 30px;
  }
</style>