<!DOCTYPE html>
<html>

<head>
	<meta charset="utf-8">
	<meta http-equiv="X-UA-Compatible" content="IE-edge">
	<meta name="viewport" content)="width=device-width, initial-scale=1.0">
	<title>Responsive login</title>
	<link href='https://unpkg.com/boxicons@2.1.4/css/boxicons.min.css' rel='stylesheet'>
	<!-- <link rel="stylesheet" href="reponsive.css"> -->
	<style>
	@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700;800;900&display=swap');
*{
	margin: 0;
	padding: 0;
	box-sizing: border-box;
	font-family: 'Poppins', sans-serif;
}

body {
	display: flex;
	justify-content: center;
	align-items: center;
	min-height: 100vh;
	background: linear-gardient(90deg, #e2e2e2, #c9d6ff);
}

.container {
	position: relative;
	width: 850px;
	height: 550px;
	background: #fff;
	border-radius: 30px;
	box-shadow: 0 0 30px rgba(0, 0, 0, .2);
	margin: 20px;
	overflow: hidden;
}

.form-box {
	position: absolute;
	right: 0;
	width: 50%;
	height: 100%;
	background: #fff;
	display: flex;
	align-items: center;
	color: #333;
	text-align: center;
	padding: 40px;
	z-index: 1;
	transition: .6s ease-in-out 1.2s, visibility 0s 1s;
}

.container.active .form-box {
	right: 50%;
}

.form-box.register {
	visibility: hidden;
}

.container.active .form-box.register {
	visibility: visible;
}

form {
	width: 100%;
}

.container h1 {
	font-size: 36px;
	margin: -10px 0;
}

.input-box {
	position: relative;
	margin: 30px 0;
}

.input-box input {
	width: 100%;
	padding: 13px 50px 13px 20px;
	background: #eee;
	border-radius: 8px;
	border: none;
	outline: none;
	font-size: 16px;
	color: #333;
	font-weight: 500;
}

.input-box input::placeholder {
	color: #888;
	font-weight: 400;
}

.input-box i {
	position: absolute;
	right: 20px;
	top: 50%;
	transform: translateY(-50%);
	font-size: 20px;
	color: #888;
}

.forgot-link {
	margin: -15px 0 15px;
}

.forgot-link a {
	font-size: 14.5px;
	color: #333;
	text-decoration: none;
}

.btn {
	width: 100%;
	height: 48px;
	background: #7494ec;
	border-radius: 8px;
	box-shadow: 0 0 10px rgba(0, 0, 0, .1);
	border: none;
	cursor: pointer;
	font-size: 16px;
	color: #fff;
	font-weight: 600;
}

.container p {
	font-size: 14.5px;
	margin: 15px 0;
}

.social-icons {
	display: flex;
	justify-content: center;
}

.social-icons a {
	display: inline-flex;
	padding: 10px;
	border: 2px solid #ccc;
	border-radius: 8px;
	font-size: 24px;
	color: #333;
	text-decoration: none;
	margin: 0 8px;
}

.toggle-box {
	position: absolute;
	width: 100%;
	height: 100%;
	/* background: purple; */
}

.toggle-box::before {
	content: '';
	position: absolute;
	left: -250%;
	width: 300%;
	height: 100%;
	background: #7494ec;
	border-radius: 150px;
	z-index: 2;
	transition: 1.8s ease-in-out;
}

.container.active .toggle-box::before {
	left: 50%;
}

.toggle-panel {
	position: absolute;
	width: 50%;
	height: 100%;
	color: #fff;
	display: flex;
	flex-direction: column;
	justify-content: center;
	align-items: center;
	z-index: 2;
	transition: .6s ease-in-out;
}

.toggle-panel.toggle-left {
	left: 0;
	transtion-deplay: 1.2s;
}

.container.active .toggle-panel.toggle-left {
	left: -50%;
	transition-deplay: .6s;
}

.toggle-panel.toggle-right {
	right: -50%;
	transition-deplay: .6s;
}

.container.active .toggle-panel.toggle-right {
	right: 0;
	transtion-deplay: 1.2s;
}

.toggle-panel p {
	margin-bottom: 20px;
}

.toggle-panel .btn {
	width: 160px;
	height: 46px;
	/* background: seagreen; */
	border: 2px solid #fff;
	box-shadow: none;
}

@media screen and (max-width: 685px) {
	.container {
		height: calc(100vh - 40px);
	}
	
	.form-box {
		/* background: purple; */
		bottom: 0;
		width: 100%;
		height: 70%;
	}
	
	.container.active .form-box {
		right: 0;
		bottom: 30%;
	}
	
	.toggle-box::before {
		left: 0;
		top: -270%;
		width: 100%;
		height: 300%;
		border-radius: 20vw;
	}
	
	.container.active .toggle-box::before {
		left: 0;
		top: 70%;
	}
	
	.toggle-panel {
		/* border: 2px solid red; */
		width: 100%;
		height: 30%;
	}
	
	.toggle-panel.toggle-left {
		top: 0;
	}
	
	.container.active .toggle-panel.toggle-left {
		left: 0;
		top: -30%;
	}
	
	.toggle-panel.toggle-right {
		right: 0;
		bottom: -30%;
	}
	.container.active .toggle-panel.toggle-right {
		bottom: 0;
	}
}

@media screen and (max-width: 400px) {
	.form-box {
		padding: 20px;
	}
	
	.toggle-panel h1 {
		font-size: 30px;
	}
}
	</style>
</head>

<body>
	
	<div class="container">
		<div class="form-box login">
			<form action="">
				<h1>Login</h1>
				<div class="input-box">
					<input type="text" placeholder="Username" required>
					<i class='bx bxs-user'></i>
				</div>
				<div class="input-box">
					<input type="password" placeholder="Password" required>
					<i class='bx bxs-lock-alt'></i>
				</div>
				<div class="forgot-link">
					<a href="#">Forgot password?</a>
				</div>
				<button type="submit" class="btn" >Login</button>
				<p>or login with social platforms</p>
				<div class="social-icons">
					<a href="#"><i class='bx bxl-google'></i></a>
					<a href="#"><i class='bx bxl-facebook' ></i></a>
					<a href="#"><i class='bx bxl-github' ></i></a>
					<a href="#"><i class='bx bxl-linkedin' ></i></a>
					<a href="#"><i class='bx bxl-apple' ></i></a>
				</div>
			</form>
		</div>	
	
		<div class="form-box register">
			<form action="">
				<h1>Registration</h1>
				<div class="input-box">
					<input type="text" placeholder="Username" required>
					<i class='bx bxs-user'></i>
				</div>
				<div class="input-box">
					<input type="email" placeholder="Email" required>
					<i class='bx bxs-envelope' ></i>
				</div>
				<div class="input-box">
					<input type="password" placeholder="Password" required>
					<i class='bx bxs-lock-alt'></i>
				</div>
				
				<button type="submit" class="btn" >Register</button>
				<p>or register with social platforms</p>
				<div class="social-icons">
					<a href="#"><i class='bx bxl-google'></i></a>
					<a href="#"><i class='bx bxl-facebook' ></i></a>
					<a href="#"><i class='bx bxl-github' ></i></a>
					<a href="#"><i class='bx bxl-linkedin' ></i></a>
					<a href="#"><i class='bx bxl-apple' ></i></a>
				</div>
			</form>
		</div>
		
		<div class="toggle-box">
			<div class="toggle-panel toggle-left">
				<h1>Hello, Welcome !</h1>
				<p>Dont't have an account?</p>
				<button class="btn register-btn">Register</button>
			</div>
			<div class="toggle-panel toggle-right">
				<h1>Welcome Back!</h1>
				<p>Already have an account?</p>
				<button class="btn login-btn">Login</button>
			</div>
		</div>
	</div>	
	
	<script> const container = document.querySelector('.container');
const registerBtn = document.querySelector('.register-btn');
const loginBtn = document.querySelector('.login-btn');

registerBtn.addEventListener('click',() => {
	container.classList.add('active');
});

loginBtn.addEventListener('click',() => {
	container.classList.remove('active');
});</script>
	
</body>

</html>
