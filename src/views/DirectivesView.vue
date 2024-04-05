<template>
  <section class="m-4">
  <h2 class="text-center">{{ message }}</h2>

  <h3>Директива v-model</h3>
  <form action="#" method="POST">
    <input v-model="login" class="p-1" type="text" name="login" value="" placeholder="Введите логин">
    <p>Ваш логин: {{ login }}</p>
  </form>

  <h3>Директива v-if</h3>
  <div v-if="seen">
    <p>Этот блок виден, так как переменная seen - истина</p>
    <p>А второй блок убран из DOM-дерева</p>
  </div>
  <div v-if="!seen">
    <p>Этот блок не виден, так как переменная seen - ложна</p>
    <p>Он убран из DOM-дерева</p>
  </div>

  <h3>Директива v-show</h3>
  <div v-show="seen">
    <p>Этот блок виден, так как переменная seen - истина</p>
    <p>А второй блок скрыт с помощью свойства display</p>
  </div>
  <div v-show="!seen">
    <p>Этот блок не виден, так как переменная seen - ложна</p>
    <p>К нему добавлен атрибут style="display: none;"</p>
  </div>

    <h3>Директива v-for (массив)</h3>
    <div>
      <p>Список фрутов: </p>
      <ol>
        <li v-for="fruit in fruits">{{ fruit }}</li>
      </ol>
    </div>

  <h3>Директива v-for (массив объектов)</h3>
  <div>
  <p>Список студентов: </p>
    <ol>
      <li v-for="student in students">
        ФИО: <b>{{ student.fio }}</b> <br />
        Дата рождения: {{ student.birth }} <br />
        Пол: {{ student.sex }} <br />
      </li>
    </ol>
  </div>

    <h3>Директива v-bind</h3>
    <div>
      <img v-bind:src="bind_img" alt="Картинка" width="300">
      <br />
      <input style="text-align: center; background-color: pink" type="text" :value="bind_value" disabled>
    </div>

    <h3 class="mt-3">Директива v-on</h3>
    <div>
      <Button v-on:click="click_green" class="btn btn-success w-25">Кнопка 1</Button>
      <Button @click="click_red" class="btn btn-danger m-1 w-25">Кнопка 2</Button>
    </div>

  </section>
</template>

<style scoped>
  input{
    width: 300px;
  }
</style>

<script>
import Button from "@/components/Button.vue";
  export default {
    components: {Button},
    //Переменная
    data() {
      return{
        message: 'Приветствую вас на курсе по изучению фреймфорка Vue 3!',
        login: null,
        seen: true,
        fruits: ["Яблоко", "Груша", "Мурад", "Апельсин", "Банан"],
        students: [
            {
              fio: 'Евсеев Дмитрий Витальевич',
              birth: '04.11.2005',
              sex: 'Мужской'
            },
            {
              fio: 'Буйкин Андрей Анатольевич',
              birth: '20.12.2005',
              sex: 'Мужской'
            },
            {
              fio: 'Шейкина Елизавета Викторовна',
              birth: '23.04.2005',
              sex: 'Женский'
            }
        ],
        bind_img: "https://media.stickerswiki.app/cutekitttens/4889.512.webp",
        bind_value: "Милый котик",
      }
    },
    methods: {
      click_green(){
        alert("Вы нажали первую кнопку")
      },
      click_red(){
        alert("Вы нажали вторую кнопку")
      },
    }
  }
</script>
<style scoped>

</style>