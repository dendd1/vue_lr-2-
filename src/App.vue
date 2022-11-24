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
              <input v-model="photo" class="input-site border fs-5 p-2 " type="text">
            </div>
          </div>


          <div class="row">
            <div class="col-3">
              <p class="fs-5">Телефон</p>
            </div>
            <div class="col-9">
              <input v-model="phone" @input="validatePhone" class="input-site border fs-5 p-2 " type="text">
              <p class="fs-5 text-danger" style="width: 400px">{{ erPhone }}</p>
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
              <textarea v-model="about" class="input-site border fs-5 p-2" style="height: 200px;" maxlength="350"
                        rows="7"></textarea>
            </div>
          </div>

          <div class="row">
            <div class="col-3">
              <p class="fs-5">Образование</p>
            </div>
            <div class="col-9">
              <!--              <input v-model="education" class="input-site border fs-5 p-2 " type="text">-->
              <select v-model="education" class="input-site border fs-5  ">
                <option>Среднее</option>
                <option>Среднее специальное</option>
                <option>Неоконченное высшее</option>
                <option>Высшее</option>
              </select>
            </div>

          </div>
          <div v-if="education != 'Среднее'">
          <div class="row">
            <div class="col-3">
              <p class="fs-5">Учебное заведение</p>
            </div>
            <div class="col-9">
              <input v-model="institution" class="input-site border fs-5 p-2 " type="text">
            </div>

          </div>

          <div class="row">
            <div class="col-3">
              <p class="fs-5">Факультет</p>
            </div>
            <div class="col-9">
              <input v-model="faculty" class="input-site border fs-5 p-2 " type="text">
            </div>

          </div>

          <div class="row">
            <div class="col-3">
              <p class="fs-5">Специализация</p>
            </div>
            <div class="col-9">
              <input v-model="specialization" class="input-site border fs-5 p-2 " type="text">
            </div>

          </div>

          <div class="row">
            <div class="col-3">
              <p class="fs-5">Год окончания</p>
            </div>
            <div class="col-9">
              <input v-model="Year_ending" type="number" class="input-site border fs-5 p-2 " maxlength="4" min="1950" max="2099" step="1"  />
            </div>

          </div>





          </div>
          <div class="row">
            <div class="col-3">
              <p class="fs-5">Ключевые навыки</p>
            </div>
            <div class="col-9">
              <textarea v-model="skills" class="input-site border fs-5 p-2" style="height: 200px;" maxlength="150"
                        rows="7"></textarea>
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
            <p class="fs-5">{{ surname }} {{ name }} {{ patronymic }} - {{ profession }}</p>
            <p class="fs-5" v-if="erPhone.length > 0">{{ mail }}</p>
            <p class="fs-5" v-else>{{ mail }} (тел.: +7{{ phone }})</p>
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
          <p class="fs-5">Навыки: {{ skills }}</p>
          <p class="fs-5">Образование: {{ education }}</p>
          <div v-if="education != 'Среднее'">
            <p class="fs-5">Учебное заведение: {{ institution }}</p>
            <p class="fs-5">Факультет: {{ faculty }}</p>
            <p class="fs-5">Специализация: {{ specialization }}</p>
            <p class="fs-5">Год окончания: {{ Year_ending }}</p>
          </div>
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
      institution: 'МГЧПУМ (бывший тракторно-космический завод)',
      faculty: 'ФРАТ (факультет рассада автоматических технологий)',
      specialization: 'бухгалтер рассады',
      Year_ending: '2022',
      erPhone: '',
      profession: 'бухгалтер',
      city: 'Чайхона',
      photo: 'https://s00.yaplakal.com/pics/pics_original/5/9/2/14163295.jpg',
      surname: 'Духанов',
      name: 'Данила',
      patronymic: 'Иванович',
      phone: '9005553535',
      mail: 'test@mail.ru',
      bDate: '2022-11-22',
      education: 'Среднее',
      money: '7777',
      skills: 'умный; крутой; соленый; лунный; космический; стрессолётный;',
      about: 'Вспоминаю свой первый опыт выращивания рассады, это было и волнительно, и радостно одновременно: появилось новое увлекательное хобби – овощеводство. В первый же год вырастила хорошую рассаду томатов, перцев, баклажанов, лука-порея.\n' +
          'В статье собрала свои наблюдения как новичка, надеюсь, будет полезно почитать начинающим дачникам.',
    }
  },
  methods: {
    validatePhone() {
      this.erPhone = '';
      if (this.phone.length < 6 || this.phone.length > 10) {
        this.erPhone = 'Длина телефона должна быть от 6 до 10 символов.';
      }
      if (/\D/.test(this.phone)) {
        this.erPhone += ' Номер должен сожержать только цифры.';
      }
    }

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
  width: 480px;
}

.photo {

}
</style>