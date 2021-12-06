<template>
  <div class="pessoa container mt-3">
    <h3>Dados Pessoas</h3>
    <hr>
    <b-form>
      <b-row>
        <b-col md="4" sm="12">
          <b-form-group
            label="Nome:"
            label-for="nome"
          >
            <b-form-input
              v-model="form.nome"
              id="nome"
              placeholder="Ex: João Silva"
            ></b-form-input>
          </b-form-group>
        </b-col>
        <b-col md="5" sm="12">
          <b-form-group
            label="E-mail:"
            label-for="email"
            description="Seu e-mail deve ser único"
          >
            <b-form-input
              v-model="form.email"
              id="email"
              placeholder="Ex: joao@teste.com"
            ></b-form-input>
          </b-form-group>
        </b-col>
        <b-col md="3" sm="12">
          <b-form-group
            label="Status:"
            for="status"
          >
            <b-form-radio-group
              id="status"
              v-model="form.status"
            >
              <b-form-radio value="active"> Ativo</b-form-radio>
              <b-form-radio value="inactive"> Inativo</b-form-radio>
            </b-form-radio-group>
          </b-form-group>
        </b-col>
      </b-row>
      <b-row>
        <b-col md="4" sm="12">
          <b-form-group
            label="CPF:"
            label-for="cpf"
          >
            <b-form-input
              v-model="form.cpf"
              id="cpf"
              placeholder="Ex: 999.999.999-99"
            ></b-form-input>
          </b-form-group>
        </b-col>
        <b-col md="3" sm="12">
          <b-form-group
            label="RG:"
            label-for="rg"
          >
            <b-form-input
              v-model="form.rg"
              id="rg"
              placeholder="Ex: 99999999"
            ></b-form-input>
          </b-form-group>
        </b-col>
        <b-col md="5" sm="12">
          <b-form-group
            label="Data de Nascimento" label-for="dataDeNascimento"
          >
            <b-form-datepicker
              v-model="form.dataDeNascimento"
              id="dataDeNascimento"
              placeholder="01/01/2022"
            ></b-form-datepicker>
          </b-form-group>
        </b-col>
      </b-row>
      <h3>Localização</h3>
      <hr>
      <b-row>
        <b-col md="4" sm="12">
          <b-form-group label="País:" label-for="pais">
            <b-form-select
              id="pais"
              v-model="form.pais"
              :options="paises"
            ></b-form-select>
          </b-form-group>
        </b-col>
        <b-col md="4" sm="12">
          <b-form-group label="Estado:" label-for="estado">
            <b-form-select
              id="estado"
              v-model="form.estado"
              :options="estados"
            ></b-form-select>
          </b-form-group>
        </b-col>
        <b-col md="4" sm="12">
          <b-form-group label="Cidade:" label-for="cidade">
            <b-form-select
              id="cidade"
              v-model="form.cidade"
              :options="cidades"
            ></b-form-select>
          </b-form-group>
        </b-col>
      </b-row>
      <h3>Anexos</h3>
      <hr>
      <b-row>
        <b-col md="6" sm="12">
          <b-form-file
            @input="saveFile"
            v-model="form.file"
            placeholder="Selecione uma imagem"
          ></b-form-file>
        </b-col>
      </b-row>
    </b-form>
    <b-card class="mt-3" header="Resultado">
      <pre class="m-0">
        {{ form }}
      </pre>
    </b-card>
  </div>
</template>
<script>
export default {
  name: "Pessoa",
  data() {
    return {
      form: {
        nome: null,
        email: null,
        status: null,
        cpf: null,
        rg: null,
        dataDeNascimento: null,
        pais: null,
        estado: null,
        cidade: null,
        file: ""
      },
      paises: [
        {
          value: null, text: "Selecione uma opção"
        },
        {
          value: "br", text: "Brasil"
        },
        {
          value: "us", text: "EUA"
        },
        {
          value: "col", text: "Colombia"
        }
      ],
      estados: [
        {
          value: null, text: "Selecione uma opção"
        },
        {
          value: "PA", text: "Pará"
        }
      ],
      cidades: [
        {
          value: null, text: "Selecione uma opção"
        },
        {
          value: "Belém", text: "Belém"
        }
      ]
    }
  },
  methods: {
    saveFile(event) {
      console.log(event)
      this.form.file = event.name
    }
  }
}
</script>
