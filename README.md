<style>
	.logo {
    margin: auto;
    font-size: 20px;
    background: white;
    padding: 7px 11px;
    border-radius: 50% 50%;
    color: #000000b3;
}
nav .nav-link{
	color:white !important;
	

}
nav .nav-item{
	width: auto !important
}
@media (min-width: 992px){
	.navbar-expand-lg .navbar-nav {
	    flex-direction: row;
	}
}
</style>
<div class="main">
<nav class="navbar fixed-top navbar-expand-lg navbar-dark bg-primary">
		<a class="navbar-brand" href="./">WESEE</a>
    <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
        <span class="navbar-toggler-icon"></span>
    </button>
    <div class="collapse navbar-collapse" id="navbarSupportedContent">
        <form class="form-inline mx-auto my-2">
            <input class="form-control mr-sm-1" type="search" placeholder="Search" aria-label="Search">
            <button class="btn btn-outline-success my-2 my-sm-0" type="submit">Search</button>
        </form>
		<ul class="navbar-nav">
            <li>
                <a class="nav-link" href="index.php?page=home">Home<span class="sr-only"></span></a>
				<?php if(isset($_SESSION['login_id'])): ?>
            </li>
			<li>
                <a class="nav-link" href="index.php?page=my_uploads">My Uploads<span class="sr-only"></span></a>
            </li>
                <li class=" dropdown nav-item">
                	<a href="#" class="text-white dropdown-toggle nav-link"  id="account_settings" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false"><?php echo ucwords($_SESSION['login_firstname'].' '.$_SESSION['login_middlename']) ?> </a>
	              <div class="dropdown-menu" aria-labelledby="account_settings" style="left: -2.5em;">
	                <a class="dropdown-item" href="index.php?page=signup&id=<?php echo $_SESSION['login_id'] ?>" id=""><i class="fa fa-cog"></i> Manage Account</a>
	                <a class="dropdown-item" href="ajax.php?action=logout"><i class="fa fa-power-off"></i> Logout</a>
	              </div>
	            </li>
                </div>
            </li>
              <?php else: ?>
	            <li class="nav-item"><a class="nav-link js-scroll-trigger" href="javascript:void(0)" id="login_now">Login</a></li>
	          <?php endif; ?>
	           
        </ul>
   
</nav>


<script>
  $('#login_now').click(function(){
    uni_modal("LOGIN",'login.php')
  })
  $('#search').keypress(function(e){
  	if(e.which == 13){
  		location.href = "index.php?s="+$(this).val()
  	}
  })
</script>

<footer class="bg-primary text-center text-white fixed-bottom">
    <!-- Grid container -->
    <div class="container">
    </div>

    <div class="text-center p-3" style="background-color: rgba(0, 0, 0, 0.2);">
        © 2023 Copyright:
        <a class="text-white" href="">s&p</a>
    </div>
    <!-- Copyright -->
</footer>
<!-- Footer -->
