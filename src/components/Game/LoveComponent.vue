 <template>
	<body>
		<div id="content-box" class="shadow-lg p-5  bg-white rounded ">
			<h1>Love Calculator</h1>
			<p>Enter your name and your crush's name to see the chance that this relationship will work out:</p>
			<br/>
			<label for="your-name">Your Name:</label>
			<input type="text" id="your-name" class="m-2 border- rounded" v-model="yourName" required name="your-name"/><br/><br/>
	
			<label for="crush-name">Crush's Name:</label>
			<input type="text" id="crush-name" class="m-2 border- rounded" v-model="crushName" required name="crush-name"/><br/><br/>
	
			<button class="btn btn-info" id="calculate" @click="calculateLove">Calculate</button><br/><br/>
			<h4>{{ resultMessage }}</h4>
			<p class="fs-1 h3 text-center">{{ resultpercentage }}</p>
			
		</div>
	</body>
</template>

<script>
export default {

    data(){
        return{
            yourName: "",
            crushName: "",
			resultMessage:null,
			resultpercentage:null

            
        }
    },
    methods: {
        calculateLove  (){	
            let yourName = this.yourName;
            let crushName = this.crushName;
        
            if (yourName != "" && crushName != "") {
                let percentage = Math.floor(Math.random() * 101);
				this.resultMessage=yourName +" "+ "and" + " "+ crushName +" " + "'s chance of love: " ; 
				this.resultpercentage= percentage.toString() + "%";
            } 
        
        }
    }

}
</script>

<style scoped>
    body{
	font-family: Arial, Helvetica, sans-serif;
	text-align: center;
	background-image: url('../../assets/love.jpg');
	background-size: cover;
	background-repeat: no-repeat;
	height: 100vh;
	width: 100%;
	font-family:Verdana, Geneva, Tahoma, sans-serif
}

#content-box{
	width: 600px;
	height: 500px;
	/* background-color: whitesmoke; */
	padding: 20px;
	margin: 0 auto;
	border-radius: 10px
}

/* #calculate{
	width: 150px;
	height: 50px;

	background-color: pink;
	color: white;
	font-size: 20px;
	border: none;
	border-radius: 18px;	
} */

/* #result-percentage{
	font-size: 100%;
	text-align: center; */
/* } */
</style>