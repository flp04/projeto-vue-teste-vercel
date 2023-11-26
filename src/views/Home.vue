<template>
  <main id="main" class="main">

    <div class="pagetitle">
      <h1>Dashboard</h1>
      <nav>
        <ol class="breadcrumb">
          <li class="breadcrumb-item"><a href="index.html">Home</a></li>
          <li class="breadcrumb-item active">Dashboard</li>
        </ol>
      </nav>
    </div><!-- End Page Title -->

    

  </main><!-- End #main -->
</template>

<script>

export default {
  name: 'Home',
  components: {},
  mounted() {
    fetch('https://flpserver.000webhostapp.com/api_organizador.php?requisicao=pegarTarefas',
        {
          method: 'GET',
        }
      )
      .then(response => response.json())
      .then(data => {
        console.log(data)
        // this.obj.tarefas = data
        // this.gerarGrafico(data)
        // this.gerarGraficoItensFormulario(data)
      })
      .catch(error => {
        console.error('Ocorreu um erro:', error);
      })
  }
}

</script>

<style scoped>

/*--------------------------------------------------------------
# Main
--------------------------------------------------------------*/
#main {
  margin-top: 60px;
  padding: 20px 30px;
  transition: all 0.3s;
}

@media (max-width: 1199px) {
  #main {
    padding: 20px;
  }
}

/*--------------------------------------------------------------
# Dashboard
--------------------------------------------------------------*/
/* Filter dropdown */
.dashboard .filter {
  position: absolute;
  right: 0px;
  top: 15px;
}

.dashboard .filter .icon {
  color: #aab7cf;
  padding-right: 20px;
  padding-bottom: 5px;
  transition: 0.3s;
  font-size: 16px;
}

.dashboard .filter .icon:hover,
.dashboard .filter .icon:focus {
  color: #4154f1;
}

.dashboard .filter .dropdown-header {
  padding: 8px 15px;
}

.dashboard .filter .dropdown-header h6 {
  text-transform: uppercase;
  font-size: 14px;
  font-weight: 600;
  letter-spacing: 1px;
  color: #aab7cf;
  margin-bottom: 0;
  padding: 0;
}

.dashboard .filter .dropdown-item {
  padding: 8px 15px;
}

</style>