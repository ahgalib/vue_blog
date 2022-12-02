<template>
  <header>
    <nav class="container">
      <div class="branding">
          <RouterLink :to="{name:'home'}">FireBlogs</RouterLink>
      </div>
      <div class="nav-links">
        <ul v-show="!mobile">
          <RouterLink :to="{name:'home'}" class="navh">Home</RouterLink>
          <RouterLink to="/about"  class="navh">About</RouterLink>
          <RouterLink to=""  class="navh">Create Post</RouterLink>
          <RouterLink to=""  class="navh">Login/Register</RouterLink>
        </ul>
      </div>
    </nav>

    <div class="manu-icon-div" @click="toggleMobileNav()" v-show="mobile">
      <div class="manu-icon"></div>
      <div class="manu-icon2"></div>
      <div class="manu-icon3"></div>
    </div>

    <transition name="mobile-nav">
      <ul class="mobile-nav" v-show="mobileNav">
        <RouterLink :to="{name:'home'}" class="navh">Home</RouterLink>
        <RouterLink to="/about"  class="navh">About</RouterLink>
        <RouterLink to=""  class="navh">Create Post</RouterLink>
        <RouterLink to=""  class="navh">Login/Register</RouterLink>
      </ul>
    </transition>

  </header>
    
</template>

<script>
export default{
  name:"Navbar",
  data:function(){
    return{
      mobile:null,
      mobileNav:null,
      windownWidth:null,
    }
  },
  created:function(){
    window.addEventListener('resize',this.checkScreen);
    this.checkScreen();
  },
  methods:{
    checkScreen:function(){
      let width = this.windownWidth = window.innerWidth;
      //alert(width);
      if(width <=750){
        this.mobile = true;
        this.mobileNav = true;
        return;
      }else{
        this.mobile= false;
        this.mobileNav = false;
        return;
      }
    },
    toggleMobileNav:function(){
      this.mobileNav = !this.mobileNav;
    }
  }
}

</script>

<style scoped>
header{
  width:100%;
  height:40px;
  background-color:#fff;
  padding:0 25px;
  z-index: 99;
}
nav{
  display:flex;
 
  padding:25px 0;
  
}

.navh{
  
  padding:0 10px;

  font-weight: 500;
  transition:0.3s color ease;
  
}
.navh:hover{
  color:crimson;
  background-color: rgb(224, 221, 17);
}
.branding{
  display:flex;
  align-items:center;
  font-weight:bolder;
}
.nav-links{
  position:relative;
  display:flex;
  flex:1;
  align-items: center;
  justify-content: flex-end;
}
.nav-links ul{
  margin-right:32px;
}
.nav-links ul .navh{
  margin-right:32px;
}
.nav-links ul .navh:last-child{
  margin-right:0
}
.manu-icon-div{
  cursor:pointer;
  position:absolute;
  top:0px;
  right:25px;
}

.manu-icon{
  width:30px;
  height:5px;
  background-color: black;
  margin-bottom:2px;
  cursor:pointer;
  position:absolute;
  top:32px;
  right:25px;
}

.manu-icon2{
  width:30px;
  height:5px;
  background-color: black;
  margin-bottom:2px;
  cursor:pointer;
  position:absolute;
  top:39px;
  right:25px;
}
.manu-icon3{
  width:30px;
  height:5px;
  background-color: black;
  margin-bottom:2px;
  cursor:pointer;
  position:absolute;
  top:46px;
  right:25px;
}

.mobile-nav{
  padding:20px;
  width:70%;
  max-width:250px;
  display:flex;
  flex-direction: column;
  position: fixed;
  height:100%;
  top:0;
  background-color: #303030;
  left:0;
}
.mobile-nav .navh{
  padding:15px 0;
  color:white;
}
</style>