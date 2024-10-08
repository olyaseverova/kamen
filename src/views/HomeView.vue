<template>
  <div class="home">
    <section class="left-side none">
      <ul class="pdfs-list list">
        <li class="pdfs-list__item" v-for="pdf in pdfs" :key="pdf.id">
          <a :href="pdf.link" class="pdf-link" target="_blank">
            {{ pdf.name }}
          </a>
        </li>
      </ul>
    </section>

    <section class="center">
      <div class="text-box">
        <button class="menu-button" type="button"></button>
        <div>
          <h1 сlass="headline-1">ПОСАДСКИЙ КАМЕНЬ</h1>
          <p class="under-headline">ПРОИЗВОДИТЕЛЬ КАЧЕСТВЕННОЙ ПЛИТКИ</p>
          <p class="place">Московская область, г. Сергиев Посад, ул. Фестивальная, 6А</p>
        </div>
        <div class="menu-wrapper" @click="openMenu">
          <div class="hamburger-menu"></div>
        </div>
      </div>

      <div class="numbers">
        <div class="number-wrap">
          <h3 class="h3-headline">Опт:</h3>
          <h3 class="number"><a href="tel:+79269255557">+7 (926) 625-55-57</a></h3>
        </div>
        <div class="number-wrap">
          <h3 class="h3-headline">Розница:</h3>
          <h3 class="number"><a href="tel:+79266255557">+7 (926) 625-55-57</a></h3>
        </div>
      </div>

      <ul class="sections-list list">
        <li class="sections-list__item" v-for="section in sections" :key="section.id">
          <a class="section-link" @click="scrollToAnchor(section.link)">{{ section.name }}</a>
        </li>
      </ul>

      <section class="about" ref="about">
        <img class="pdf-icon" src="@/img/plitka2.jpg" alt="Плитка" />
        <div class="description fade-in">
          <p class="text bold">О нас</p>
          <p class="text mb30">
            Производственное предприятие Посадский Камень основано в 1999 года. Основным профилем
            является производство вибролитой тротуарной плитки премиального качества. Помимо плитки и
            брусчатки предприятие производит бетонную фасадную отделку, лепной декор и малые
            архитектурные формы из искусственного камня.</p>
          <p class="text mb30">Наше предприятие ориентировано на продажи через дилеров. Мы являемся надежным
            поставщиком тротуарной плитки во множество магазинов Московской области.</p>
          <p class="text mb30">Обладаем собственным автопарком для доставки продукции на розничные точки партнеров.</p>
          <p class="text mb30">Наша вибролитая продукция является самой качественной в России и производится в строгом
            соответствии с ГОСТом.</p>
          <p class="text">В настоящий момент мы активно расширяем дилерскую сеть в Московской области и ищем новые
            розничные точки сбыта.</p>
        </div>
      </section>

      <ul class="statistics-list list">
        <li class="statistics-list__item" v-for="statistic in statistics" :key="statistic.id">
          <h3 class="statistic-number">{{ statistic.number }}</h3>
          <p class="statistic-text">{{ statistic.text }}</p>
        </li>
      </ul>

      <section class="principles fade-in">
        <p class="headline text bold text-center">Принципы работы предприятия</p>
        <p class="text mb30 principles-desc">Наше предприятие максимально ориентировано на розничные продажи в небольших и средних
          несетевых и мелкосетевых строительных магазинах в Московской области. Мы работаем по
          принципу B2B. Наши достоинства для дилеров:</p>

        <ul class="principles-list list">
          <li class="principles-list__item" v-for="principle in principles" :key="principle.id">
            <div class="principle-dot"></div>
            <p class="principles-text">{{ principle }}</p>
          </li>
        </ul>
      </section>


      <section class="reviews">
        <p class="headline text bold text-center">Отзывы дилеров</p>

        <ul class="reviews-list list">
          <li class="reviews-list__item" v-for="review in reviews" :key="review.id">
            <div class="review-wrap">
              <img class="review-icon" :src="review.src" alt="Иконка Дилера" />
              <p class="review-text">{{ review.text }}</p>
            </div>
            <p class="review-name">{{ review.name }}</p>
          </li>
        </ul>
      </section>

      <section class="guarantee">
        <p class="headline text bold text-center" ref="guarantee">Гарантия качества</p>
        <div class="guarantee-wrap">
          <div class="description">
            <p class="text">
              Предприятие «Посадский Камень» специализируется на производстве вибролитой продукции
              премиального качества, достигаемое за счет строгого внутреннего технического контроля,
              использования самого чистого в России бездобавочного портландцемента марки ЦЕМ 0 52,5Н
              (М600Д0), чистейшего мытого песка и высококачественных немецких пигментов LANXESS.
            </p>
            <p class="text">Отдельные заказные позиции мы изготавливаем из лучшего в мире египетского белого цемента
              Aalborg White CEM I 52,5.</p>
            <p class="text">Идеальная геометрия достигается за счет жесткой выбраковки из ротации форм после достижения
              регламентированного оборота и строгого контроля за состоянием полок этажерок.</p>
            <p class="text">Вся продукция наша продукция подвергается принудительному термогидравлическому набору
              прочности и поставляется в торговые точки в специальной герметичной упаковке, позволяющей
              дополнительно ускоренно набирать прочность.</p>
            <p class="text">
              На всю продукцию автоматически распространяется гарантия 1 год с момента продажи дилером.
            </p>
          </div>
          <img class="guarantee-icon" src="@/img/plitka.jpg" alt="Плитка" />
        </div>
      </section>

      <section class="delivery">
        <img class="delivery-icon" src="@/img/delivery.jpg" alt="Доставка" />
        <div class="delivery-wrap">
          <p class="text bold mb40">Доставка и логистика</p>
          <p class="text">Мы доставляем нашу продукцию дилерам собственными силами. В нашем распоряжении фуры
            грузоподъёмностью 20 тонн и манипуляторы до 6 тонн. Также мы практикуем доставку продукции
            непосредственно клиентам дилера по сниженной льготной стоимости.</p>
        </div>
      </section>

      <section class="styling">
        <p class="text bold mb30 text-center">Укладка</p>
        <p class="text">Для того, чтобы плитка прослужила долгие годы, закажите качественную укладку у
          профессионалов. Производственное предприятие "Посадский Камень" рекомендует
          воспользоваться услугами своей дочерней строительной организации "STEINCLUB", чьи специалисты
          аттестованы нами и рядом других производителей.</p>
      </section>
      
      <footer class="contacts" id="contacts" ref="contacts">
        <h3 class="h3">КОНТАКТЫ</h3>
        <p class="text-contacts">Нашу продукцию можно приобрести в следующих магазинах:</p>
        <iframe
          src="https://yandex.ru/map-widget/v1/?um=constructor%3Ae00c3f01b2f78cb537ea463edb102db4220ac7a9616c0c81078a27e6f8a4027d&amp;source=constructor"
          width="100%" height="423" frameborder="0"></iframe>
      </footer>
    </section>

    <section class="right-side">
      <h3 class="h3-headline">Опт:</h3>
      <h3 class="number"><a href="tel:+79269255557">+7 (926) 625-55-57</a></h3>
      <h3 class="h3-headline">Розница:</h3>
      <h3 class="number"><a href="tel:+79266255557">+7 (926) 625-55-57</a></h3>
    </section>

  </div>
</template>

<script>
export default {
  name: 'HomeView',

  data() {
    return {
      pdfs: [
        {
          name: "КАТАЛОГ",
          link: "katalog.pdf"
        },
        {
          name: "ПРАЙС",
          link: "price.pdf"
        },
        {
          name: "УСЛОВИЯ"
        },
        {
          name: "СЕРТИФИКАТЫ",
        },
      ],

      sections: [
        {
          name: "О НАС",
          link: "about"
        },
        {
          name: "КАЧЕСТВО ПРОДУКЦИИ",
          link: "guarantee"
        },
        {
          name: "КОНТАКТЫ",
          link: "contacts"
        },
        {
          name: "ЛИЧНЫЙ КАБИНЕТ ДИЛЕРА",
          link: "diler"
        }
      ],

      statistics: [
        {
          number: "12",
          text: "точек розничных дилеров успешно сотрудничают с нами"
        },
        {
          number: "2577",
          text: "клиентов приобрели нашу продукцию в 2023 года"
        },
        {
          number: "17000 м2",
          text: "плитки и брусчатки замощено нашими силами в 2023 году"
        },
        {
          number: "75000 м2",
          text: "продукции сделано для заказчиков в 2023 году"
        },
      ],

      principles: [
        "высокое качество продукции снижет дилерам головную боль с претензиями и рекламациями со стороны покупателей;",
        "мы четко выполняем гарантийные обязательства и решаем проблему с клиентами сами без участия магазинов;",
        "наша продукция достаточно дорогостоящая, что привлекает платёжеспособных клиентов на торговые точки дилеров",
        "мы даем общую рекламную поддержку бренда, покупатели целенаправленно ищут нашу продукцию у дилеров",
        "мы защищаем рынок и гарантируем дилеру наценку не менее 25%",
        "мы не берем дополнительную плату за доставку продукции на торговую точку дилера",
        "мы обеспечиваем дилера стендами, рекламными щитами и материалами, образцами продукции"
      ],

      reviews: [
        { src: require("@/img/karpova.jpg"), text: "Наш магазин «Камень на Ярославке» работает с Компанией «Посадский камень» с 2018 года. За время сотрудничества сложились деловые, доверительные, позитивные отношения. Коллектив Компании всегда очень внимательно и с пониманием относиться к нашим пожеланиям и просьбам. Товар всегда доставляется в срок согласно заявке. Продукция отличается хорошим качеством, разнообразием ассортимента. Коллектив находится в постоянном поиске новых фактур, цветовых решений. На площадке «Природный камень» представлена полная экспозиция продукции Компании «Посадский Камень» ИП Карпова Н.В. (Камень на Ярославке) выражает благодарность коллективу Компании за высокий профессионализм, внимание, отзывчивость, трудолюбие, готовность всегда оперативно решить вопросы и помочь, грамотные консультации и советы. Желаем коллективу предприятия дальнейших творческих успехов, профессионального роста и процветания!", name: "С уважением, ИП Карпова Н.В." },
        { src: require("@/img/stroylider.png"), text: "Работаем с производством «Посадский Камень» с 2017 года. Продукция всегда отличного качества👍. Есть гарантия, что является очень важным аргументом. Индивидуальный подход к клиентам, всегда оперативная доставка. Ребята молодцы, планируем и в дальнейшем работать с «Посадским Камнем». Нам всё нравится 👍", name: "Магазин «Строй Лидер», продавец Янченко Анна" }
      ]
    }
  },

  methods: {
    openMenu: function () {
      let hamburger = document.querySelector(".hamburger-menu");
      let leftSide = document.querySelector(".left-side");
      hamburger.classList.toggle("animate");
      leftSide.classList.toggle("none");
    },

    scrollToAnchor: function (href) {
      this.$refs[href].scrollIntoView({ behavior: "smooth" })
    },
  },
}
</script>