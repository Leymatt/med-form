<template>
  <div class="reg">
    <div class="reg__header">
      <div class="reg__header-content">
        <div class="reg__icon" />
        <h1 class="reg__title">Добавьте нового клиента</h1>
      </div>
    </div>
    <form class="reg__form" @submit="submitHandler">

      <div class="reg__form-wrapper">
        <p class="reg__form-title">Личные данные клиента</p>
        <div class="reg__form-content-wrapper">
          <div class="reg__form-content">
            <div class="reg__item">
              <label class="reg__label">
                <input class="reg__input" type="text" placeholder="Фамилия">
              </label>
              <p>*</p>
            </div>
            <div class="reg__item">
              <label class="reg__label">
                <input class="reg__input" type="text" placeholder="Имя">
              </label>
              <p>*</p>
            </div>
            <div class="reg__item">
              <label class="reg__label">
                <input class="reg__input" type="text" placeholder="Отчество">
              </label>
            </div>
            <div class="reg__item">
              <label class="reg__label">
                <input class="reg__input" type="date" placeholder="Дата рождения">
              </label>
              <p>*</p>
            </div>
            <div class="reg__item">
              <label class="reg__label">
                <input class="reg__input" type="number" placeholder="Номер телефона">
              </label>
              <p>*</p>
            </div>
            <div class="reg__radiobuttons">
              <label class="reg__label-radio">
                <input class="reg__input-radio" type="radio">
              </label>
              <p class="reg__radiobuttons-text">M</p>
              <label class="reg__label-radio">
                <input class="reg__input-radio" type="radio">
              </label>
              <p class="reg__radiobuttons-text">Ж</p>
            </div>
            <div class="reg__item">
              <label class="reg__label">
                <select v-model="client" class="reg__select">
                  <option value="" selected disabled>Группа клиентов</option>
                  <option class="reg__option" v-for="option in clients" :key="option.clients" value="option.value">{{ option.text }}</option>
                </select>
              </label>
              <p>*</p>
            </div>
            <div class="reg__item">
              <label class="reg__label">
                <select v-model="doctor" class="reg__select">
                  <option value="" selected disabled>Лечащий врач</option>
                  <option class="reg__option" v-for="option in doctors" :key="option.doctors" value="option.value">{{ option.text }}</option>
                </select>
              </label>
            </div>
            <div class="reg__radiobuttons">
              <label class="reg__label-radio">
                <input class="reg__input-radio" type="radio">
              </label>
              <p class="reg__radiobuttons-text">Не отправлять смс</p>
            </div>
          </div>
        </div>
      </div>

      <div class="reg__form-wrapper">
        <p class="reg__form-title">Адрес клиента</p>
        <div class="reg__form-content-wrapper">
          <div class="reg__form-content">
            <div class="reg__item">
              <label class="reg__label">
                <input class="reg__input" type="text" placeholder="Индекс">
              </label>
            </div>
            <div class="reg__item">
              <label class="reg__label">
                <input class="reg__input" type="text" placeholder="Страна">
              </label>
            </div>
            <div class="reg__item">
              <label class="reg__label">
                <input class="reg__input" type="text" placeholder="Область">
              </label>
            </div>
            <div class="reg__item">
              <label class="reg__label">
                <input class="reg__input" type="text" placeholder="Город">
              </label>
              <p>*</p>
            </div>
            <div class="reg__item">
              <label class="reg__label">
                <input class="reg__input" type="text" placeholder="Улица">
              </label>
            </div>
            <div class="reg__item">
              <label class="reg__label">
                <input class="reg__input" type="text" placeholder="Дом">
              </label>
            </div>
          </div>
        </div>
      </div>

      <div class="reg__form-wrapper third-area">
        <p class="reg__form-title">Документ удостоверяющий личность</p>
        <div class="reg__form-content-wrapper">
          <div class="reg__form-content">
            <div class="reg__item">
              <label class="reg__label">
                <select v-model="doc" class="reg__select">
                  <option value="" selected disabled>Тип документа</option>
                  <option class="reg__option" v-for="option in docs" :key="option.docs" value="option.value">{{ option.text }}</option>
                </select>
              </label>
            </div>
            <div class="reg__item">
              <label class="reg__label">
                <input class="reg__input" type="number" placeholder="Серия">
              </label>
            </div>
            <div class="reg__item">
              <label class="reg__label">
                <input class="reg__input" type="number" placeholder="Номер">
              </label>
            </div>
            <div class="reg__item">
              <label class="reg__label">
                <input class="reg__input" type="text" placeholder="Кем выдан">
              </label>
            </div>
            <div class="reg__item">
              <label class="reg__label">
                <input class="reg__input" type="date" placeholder="Дата выдачи">
              </label>
            </div>
          </div>
        </div>
      </div>
      <button class="reg__submit" type="submit">Сохранить</button>
    </form>
  </div>
</template>

<script>
export default {
  name: "registration",
  data () {
    return {
      client: '',
      clients: [
        {text: 'VIP', value: 'VIP'},
        {text: 'Проблемные', value: 'Проблемные'},
        {text: 'ОМС', value: 'ОМС'}
      ],
      doctor: '',
      doctors: [
        {text: 'Иванов', value: 'Иванов'},
        {text: 'Захаров', value: 'Захаров'},
        {text: 'Чернышева', value: 'Чернышева'}
      ],
      doc: '',
      docs: [
        {text: 'Паспорт', value: 'Паспорт'},
        {text: 'Свидетельство о рождении', value: 'Свидетельство о рождении'},
        {text: 'Водительское удостоверение', value: 'Водительское удостоверение'},
      ]
    }
  }
}
</script>

<style lang="scss">
 .reg {
   max-width: 1800px;
   margin: 30px auto 0;
   background: linear-gradient(179deg, #FBFFFE 0.81%, #D7F6F8 36.4%);
   border: 1px solid #31BAC2;
   box-sizing: border-box;
   border-radius: 20px;

   .reg__header {
     display: flex;
     width: 100%;
     border-bottom: 1px solid #B7F9FD;

     .reg__header-content {
       display: flex;
       margin: 35px 0 35px 75px;

       .reg__icon {
         background: url("../assets/logo.svg") top left / cover no-repeat;
         width: 65px;
         height: 60.5px;
       }

       .reg__title {
         font-size: 32px;
         line-height: 39px;
         margin-left: 30px;
         color: #6C8D8D;
         font-style: normal;
         font-weight: normal;
         align-self: center;
       }
     }
   }

   .reg__form {
     display: grid;
     grid-template-columns: repeat(3, minmax(min-content, 1fr));
     grid-gap: 0 40px;
     width: 85%;
     margin: 43px auto 43px;
     grid-template-areas: "first second third";

     .reg__form-wrapper {
       display: flex;
       flex-direction: column;
       height: fit-content;

       .reg__form-title {
         font-size: 16px;
         line-height: 20px;
         color: #313939;
         margin-left: 20px;
       }

       .reg__form-content-wrapper {
         display: flex;
         flex-direction: column;
         background: #FFFEFE;
         box-shadow: 0 4px 22px 3px #CCECEE;
         border-radius: 10px;
         margin: 20px 0 0;
         max-width: 410px;
         width: 100%;

         .reg__form-content {
           margin: 35px auto 0;
           width: 90%;

           .reg__item {
             display: flex;

             > p {
               color: red;
               margin-left: 6px;
             }

             .reg__label {
               width: 100%;
               max-width: 355px;

               .reg__input {
                 width: 100%;
                 border: 1px solid #D7F6F8;
                 box-sizing: border-box;
                 border-radius: 5px;
                 height: 40px;
                 margin-bottom: 30px;
                 padding-left: 15px;
                 font-style: normal;
                 font-weight: normal;
                 font-size: 13px;
                 line-height: 16px;
                 color: #161C1D;
               }
             }
           }

           .reg__radiobuttons {
             display: flex;
             flex-direction: row;
             width: fit-content;
             margin: 0 0 30px 15px;

             .reg__label-radio {
               height: fit-content;


               &:nth-child(3) {
                 margin-left: 35px;
               }
             }

             .reg__radiobuttons-text {
                margin-left: 14px;
                align-self: center;
             }
           }

           .reg__select {
             width: 100%;
             border: 1px solid #D7F6F8;
             box-sizing: border-box;
             border-radius: 5px;
             height: 40px;
             margin-bottom: 30px;
             padding-left: 15px;
             font-weight: 300;
             font-size: 13px;
             line-height: 16px;
             color: #161C1D;
           }

           .reg__label-radio-end {
             height: fit-content;
           }

           .reg__radiobuttons-text-end {
             margin-left: 14px;
             align-self: center;
           }
         }
       }
     }
     .third-area {
         grid-area: third / third
     }
     .reg__submit {
       max-width: 300px;
       width: 100%;
       height: 55px;
       background: #31BAC2;
       box-shadow: 0 4px 4px rgba(186, 184, 184, 0.25);
       border-radius: 5px;
       font-weight: normal;
       font-size: 20px;
       line-height: 24px;
       font-variant: small-caps;
       color: #FFFFFF;
       justify-self: end;
       margin-bottom: 45px;
       align-self: end;
       grid-area: third / third;
     }
   }
 }
</style>
