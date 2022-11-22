<template>
  <div class="m-5">



    <div class="row">
      <div class="col">
        <h1 class="fs-3 m-3">Заполните форму:</h1>
        <form>


          <div class="row">
            <div class="col-3">
              <p class="fs-5">Профессия</p>
            </div>
            <div class="col-9">
              <input v-model="profession" class="input-site border fs-5 p-2" type="text">
            </div>
          </div>

          <div class="row">
            <div class="col-3">
              <p class="fs-5">Фалимия</p>
            </div>
            <div class="col-9">
              <input v-model="surname" class="input-site border fs-5 p-2 " type="text">
            </div>
          </div>


          <div class="row">
            <div class="col-3">
              <p class="fs-5">Имя</p>
            </div>
            <div class="col-9">
              <input v-model="name" class="input-site border fs-5 p-2 " type="text">
            </div>
          </div>

          <div class="row">
            <div class="col-3">
              <p class="fs-5">Отчесво</p>
            </div>
            <div class="col-9">
              <input v-model="patronymic" class="input-site border fs-5 p-2 " type="text">
            </div>
          </div>

          <div class="row">
            <div class="col-3">
              <p class="fs-5">Город</p>
            </div>
            <div class="col-9">
              <input v-model="city" class="input-site border fs-5 p-2 " type="text">
            </div>
          </div>



          <div class="row">
            <div class="col-3">
              <p class="fs-5">Фото</p>
            </div>
            <div class="col-9">
              <input  v-model="photo" class="input-site border fs-5 p-2 " type="text">
            </div>
          </div>




          <div class="row">
            <div class="col-3">
              <p class="fs-5">Телефон</p>
            </div>
            <div class="col-9">
              <input v-model="phone" class="input-site border fs-5 p-2 " type="text">
            </div>
          </div>

          <div class="row">
            <div class="col-3">
              <p class="fs-5">Почта</p>
            </div>
            <div class="col-9">
              <input v-model="mail" class="input-site border fs-5 p-2 " type="text">
            </div>
          </div>


          <div class="row">
            <div class="col-3">
              <p class="fs-5">Дата рождения</p>
            </div>
            <div class="col-9">
              <input v-model="bDate" class="input-site border fs-5 p-2 " type="date">
            </div>
          </div>

          <div class="row">
            <div class="col-3">
              <p class="fs-5">О себе</p>
            </div>
            <div class="col-9">
              <textarea  v-model="about" class="input-site border fs-5 p-2" style="height: 200px;" maxlength="350" rows="7"></textarea>
            </div>
          </div>

          <div class="row">
            <div class="col-3">
              <p class="fs-5">Образование</p>
            </div>
            <div class="col-9">
              <input v-model="education" class="input-site border fs-5 p-2 " type="text">
            </div>
          </div>

          <div class="row">
            <div class="col-3">
              <p class="fs-5">Ключевые навыки</p>
            </div>
            <div class="col-9">
              <textarea  v-model="skills" class="input-site border fs-5 p-2" style="height: 200px;" maxlength="150" rows="7"></textarea>
            </div>
          </div>

          <div class="row">
            <div class="col-3">
              <p class="fs-5">Желаемая ЗП (Рубли)</p>
            </div>
            <div class="col-9">
              <input v-model="money" class="input-site border fs-5 p-2 " type="text">
            </div>
          </div>






        </form>
      </div>

      <div class="col">
        <h1>Ваше резюме</h1>
        <div class="row">
          <div class="col-6">
            <p class="fs-5">{{ surname }} {{name}} {{patronymic}} - {{ profession }}</p>
            <p class="fs-5">{{ mail }} {{ phone }}</p>
            <img :src="photo" class="photo img-fluid">
          </div>
          <div class="col-6">
            <p class="fs-5">{{ bDate }}</p>
            <p class="fs-5">г. {{ city }}</p>
            <p class="fs-5">О себе:</p>
            <p class="fs-5">{{ about }}</p>
          </div>
        </div>
        <div class="row">
          <p class="fs-5">Образование: {{ education }}</p>
          <p class="fs-5">Навыки:</p>
          <p class="fs-5">{{ skills }}</p>
        </div>
        <p class="fs-5 text-center">Желаемая ЗП: {{ money }} (Р)</p>

      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      profession: 'бухгалтер',
      city: 'Чайхона',
      photo: 'https://s00.yaplakal.com/pics/pics_original/5/9/2/14163295.jpg',
      surname: 'Духанов',
      name: 'Данила',
      patronymic: 'Иванович',
      phone: '89005553535',
      mail: 'test@mail.ru',
      bDate: '2022-11-22',
      education: 'Высшее МГЧПУ (бывш. тракторный полетный первокосмический колледж)',
      money: '7777',
      skills: 'умный; крутой; соленый; лунный; космический; стрессолётный;',
      about: 'Вспоминаю свой первый опыт выращивания рассады, это было и волнительно, и радостно одновременно: появилось новое увлекательное хобби – овощеводство. В первый же год вырастила хорошую рассаду томатов, перцев, баклажанов, лука-порея.\n' +
          'В статье собрала свои наблюдения как новичка, надеюсь, будет полезно почитать начинающим дачникам.',
    }
  },
  methods: {

  }
}
</script>

<style scoped>
.box {
  width: 900px;
}

.input-site {
  height: 35px;
  border-radius: 3px;
  width: 400px;
}
.photo{

}
</style>