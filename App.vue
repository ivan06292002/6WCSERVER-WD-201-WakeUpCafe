<template>
  <div>
    <!-- Nav bar -->
    <nav class="navbar navbar-expand-lg navbar-light bg-light">
      <div class="container">
        <a class="navbar-brand float-left"><h1>Wake Up Cafe</h1></a>
        <ul class="nav navbar-nav flex-row float-right">
          <li class="nav-item">
            <router-link class="nav-link pr-3" to="/"><b>Order Here</b></router-link>
          </li>
          <li class="nav-item">
            <router-link class="nav-link" to="/view"><b>Your Order</b></router-link>
          </li>
           <li class="nav-item">
            <router-link class="nav-link" to="/coffee"><b>Our Coffee</b></router-link>
            
          </li>
           <li class="nav-item">
            <router-link class="nav-link" to="/tea"><b>Our Teas</b></router-link>
          </li>
           <li class="nav-item">
            <router-link class="nav-link" to="/contact"><b>Contact</b></router-link>
          </li>
        </ul>
      </div>
    </nav>
    <!-- Router view -->
    <div class="container mt-5">
      <router-view></router-view>
    </div>
  </div>
</template>

