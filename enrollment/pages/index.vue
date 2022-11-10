<template>
  <section class="vh-100" style="background-color: #6b8f71;">

    <div class="container fluid h-100">
      <NavBar/>
      <div class="row d-flex justify-content-center h-100">
      <div class="column p-5">
        <div class="row d-flex justify-content-start align-items-center h-100">
        <div class="card image text-white mw-100 mh-100" style="border-radius: 0.5rem; width: 660px; height: 625px;">
          <div class="card-body p-5">

            <h1 class="text-center"> WELCOME </h1>
            <p class="text-center font-italic" style="font-size: 2rem;"> Plantacy </p>

          </div>
        </div>
      </div>
      </div>
      <div class="column">
      <div class="row d-flex justify-content-end align-items-center h-100">
        <div class="card text-white" style="border-radius: 0.5rem; background-color: #466362;">
          <div class="card-body p-5 text-center">

              <h2 class="fw-bold mb-2 text-uppercase">Login</h2>
              <p class="text-white-50 mb-5">Please enter your login and password!</p>

              <div class="form-outline form-white mb-4">
                <input type="email"  class="form-control form-control-lg" />
                <label class="form-label" for="typeEmailX">Email</label>
              </div>

              <div class="form-outline form-white mb-4">
                <input type="password" class="form-control form-control-lg" />
                <label class="form-label" for="typePasswordX">Password</label>
              </div>

              <p class="small mb-5 pb-lg-2"><a class="text-white-50" href="#!">Forgot password?</a></p>

              <button class="btn btn-outline-light btn-lg px-5" type="submit">LOGIN</button>

              <div class="d-flex justify-content-center text-center mt-4 pt-1">
                <a href="#!" class="text-white"><i class="fab fa-facebook-f fa-lg">facebook</i></a>
                <a href="#!" class="text-white"><i class="fab fa-twitter fa-lg mx-4 px-2">twitter</i></a>
                <a href="#!" class="text-white"><i class="fab fa-google fa-lg">google</i></a>
              </div>

            <div>
              <p class="mb-0">Don't have an account? <NuxtLink to="/registration"><a class="text-white-50 fw-bold">Sign Up</a></NuxtLink>
              </p>
            </div>

          </div>
        </div>
      </div>
      </div>
      </div>
    </div>
  </section>
</template>

<script>

import NavBar from "~/components/NavBar.vue"

export default {
  name: 'IndexPage',
  components: {NavBar,},
}
</script>


<style>
.image
{
  width: 100%;
  height: 50%;
  background-size: cover;
  background-image: url("https://scontent.fceb4-1.fna.fbcdn.net/v/t1.6435-9/129295277_5040198679338405_7831115223134395869_n.jpg?_nc_cat=100&ccb=1-7&_nc_sid=e3f864&_nc_eui2=AeHthuZzaGk167uGqzJFxkP1lye_PmtuidKXJ78-a26J0kVi6HVPWpGxhmIE2-nqDnNZ1GixsGU1Q5cY6vtSagvG&_nc_ohc=Q8DaiCNcHSYAX9pmCDY&_nc_ht=scontent.fceb4-1.fna&oh=00_AfDz9RDeaGYNOTZA8taCrbj7R0MiSKKlsEIGZtGtMHYVcQ&oe=6394487F");
}
</style>
