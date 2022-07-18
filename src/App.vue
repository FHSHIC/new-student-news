<template>
  <!-- 重要事項 -->
  <div
    id="model"
    class="fixed inset-0 z-[99] flex h-screen w-screen items-center justify-center bg-black/60 px-3 py-5"
  >
    <div
      class="relative flex w-full flex-col items-center justify-center gap-6 rounded-xl border-8 border-[#EC6261] bg-white p-12 md:max-w-lg"
    >
      <h2 class="text-center text-3xl font-bold">重要事項</h2>
      <div id="important-link" class="grid grid-cols-1 gap-4 sm:grid-cols-2">
        <a
          target="_blank"
          :href="datas[1].details[0].link"
          class="cursor-pointer rounded-md bg-[#fecb07] p-4 text-center align-middle text-lg"
        >
          {{ datas[1].details[0].title }}
        </a>
        <a
          target="_blank"
          :href="datas[1].details[1].link"
          class="flex cursor-pointer items-center justify-center rounded-md bg-[#fecb07] py-4 px-8 text-center text-lg"
        >
          <p>{{ datas[1].details[1].title }}</p>
        </a>
      </div>
      <div id="closeTag" @click="close()" class="absolute top-4 right-6">
        <span
          class="cursor-pointer text-2xl text-gray-500 hover:font-bold hover:text-black"
        >
          &times;
        </span>
      </div>
    </div>
  </div>
  <!-- 選單 -->
  <div class="fixed top-0 z-40">
    <div
      @click="jump()"
      id="list-button"
      class="fixed flex h-[9.375vw] w-full cursor-pointer items-center justify-center bg-white/20 text-[3.75vw] font-semibold text-white md:h-[36px] md:text-[14.4px]"
    >
      <p class="pointer-events-none text-center">快捷選單</p>
    </div>
  </div>
  <div
    id="jump"
    class="fixed z-50 flex max-h-screen w-[62.5vw] -translate-x-[62.5vw] flex-col items-center overflow-auto bg-[#34559D] p-[18px] duration-200 md:w-[240px]"
  >
    <div class="pointer-events-none w-[37.5vw] md:w-[144px]">
      <img src="../public/assets/Freshmen-area-content.png" alt="" />
    </div>
    <div class="h-[15px]"></div>
    <ul
      class="w-[48.125vw] text-[3.75vw] font-semibold text-white md:w-[184.8px] md:text-[14.4px]"
    >
      <li>
        <a
          v-for="list in datas[6].details"
          :href="list.link"
          :key="list.id"
          class="mb-2 flex h-[10vw] items-center justify-center rounded-[5px] bg-[#EC6261] md:h-[38.4px]"
          >{{ list.title }}
        </a>
      </li>
    </ul>
  </div>
  <!-- 封面 -->
  <div id="header" class="w-full">
    <img src="../public/assets/phone.jpeg" alt="" class="md:hidden" />
    <img src="../public/assets/computer.jpeg" alt="" class="hidden md:flex" />
  </div>
  <!-- 時程表 -->
  <div id="timeline" class="flex w-full flex-col items-center justify-center">
    <div class="w-3/4 max-w-sm pb-4 md:pb-8">
      <img
        src="../public/assets/Freshman-Admission-Schedule.png"
        class=""
        alt="新生入學時程表"
      />
    </div>
    <div
      class="flex w-full place-items-center items-center justify-center md:w-3/4"
    >
      <img
        src="../public/assets/timeline-phone.png"
        class="mx-auto md:hidden"
        alt="時程表"
      />
      <img src="../public/assets/Timeline.png" class="hidden md:flex" alt="" />
    </div>
    <div class="w-full pt-10 text-center">
      <a
        :href="datas[1].details[0].link"
        target="_blank"
        class="mx-auto flex w-[87.5vw] items-center justify-center rounded-xl bg-[#EC6261] py-5 text-[6.25vw] font-semibold text-white md:h-[80px] md:w-3/4 md:py-10 md:px-20 md:text-[24px] md:hover:border-[5px] md:hover:border-white"
      >
        <p>{{ datas[1].details[0].title }}</p>
      </a>
    </div>

    <div class="w-full">
      <img src="../public/assets/Background1.jpeg" alt="" />
    </div>
  </div>
  <!-- 新生報到 -->
  <div
    id="register"
    class="flex w-full flex-col items-center bg-[#EC6261] pb-16"
  >
    <div class="w-3/4 max-w-sm">
      <img
        src="../public/assets/Online-registration-for-new-students.png"
        alt=""
      />
    </div>
    <div
      class="grid grid-rows-3 place-items-center gap-y-[12px] bg-inherit md:grid-flow-col md:grid-rows-2 md:gap-y-0 md:gap-x-[100px] md:border-[10px] md:border-[#D85756] md:bg-[#E8C541] md:p-5"
    >
      <p
        class="text-[6.25vw] font-semibold text-[#34559D] md:row-span-1 md:text-[24px] md:leading-[28.8px]"
      >
        !!!新生請先線上報到!!!
      </p>
      <p
        class="text-[4.687vw] font-semibold text-white md:order-3 md:row-span-2 md:text-[18px] md:leading-[28.8px] md:text-[#34559D]"
      >
        (1)查詢錄取名單(報到編號)<br />(2)線上報到、上傳畢證、本土語文選課
      </p>
      <p
        class="text-center text-[6.25vw] font-semibold text-[#34559D] md:row-span-1 md:place-self-start md:text-left md:text-[24px] md:leading-[28.8px]"
      >
        逾期未報到<br />
        視同放棄錄取資格
      </p>
    </div>
    <div
      class="mt-5 grid grid-cols-1 items-center justify-center gap-5 md:grid-cols-3 md:gap-3"
    >
      <a
        v-for="check in datas[0].details"
        target="_blank"
        :href="check.link"
        :key="check.id"
        :id="check.id"
        :class="{ _disabled: isdisabled }"
        class="flex h-[62.5vw] w-[62.5vw] flex-col items-center justify-center rounded-[20px] bg-[#34559D] text-center text-[6.25vw] font-semibold leading-[7vw] md:h-[240px] md:w-[240px] md:text-[24px] md:leading-[28.8px] md:hover:border-[5px] md:hover:border-white"
      >
        <p class="pointer-events-none text-white" v-html="check.title"></p>
        <p class="pointer-events-none text-[#EC6261]" v-html="check.time"></p>
        <p class="pointer-events-none text-white" v-html="check.title2"></p>
        <p class="pointer-events-none text-[#EC6261]" v-html="check.time2"></p>
      </a>
    </div>
    <div class="h-5 md:h-10"></div>
    <div class="w-full space-y-7 text-center">
      <a
        :href="datas[1].details[1].link"
        target="_blank"
        class="mx-auto flex h-[15.625vw] w-[87.5vw] items-center justify-center rounded-xl bg-[#E8C541] text-[6.25vw] font-semibold text-white md:h-[80px] md:w-3/4 md:text-[24px] md:hover:border-[5px] md:hover:border-white"
      >
        <p>{{ datas[1].details[1].title }}</p>
      </a>
    </div>
    <div class="h-7 md:h-14"></div>
  </div>
  <!-- 說明簡報 -->
  <div
    id="briefing"
    class="relative flex w-full flex-col items-center bg-[#EC6261] pt-3"
  >
    <div class="w-3/4 max-w-sm">
      <img src="../public/assets/Admissions-Briefing.png" alt="" />
    </div>
    <div class="h-8"></div>
    <iframe
      class="h-[51.953vw] w-[78.125vw] md:h-[400px] md:w-[600px]"
      :src="datas[1].details[2].link"
      allow="autoplay"
    ></iframe>
    <div
      class="absolute left-0 bottom-28 w-[28.125vw] md:w-[216px] lg:left-16 lg:bottom-52"
    >
      <img src="../public/assets/girl.png" alt="" />
    </div>
    <div class="h-20 md:h-10"></div>
    <div
      id="line"
      class="flex w-full items-center justify-center bg-[#EC6261] pb-6 pt-10"
    >
      <a
        :href="datas[1].details[6].link"
        target="_blank"
        class="z-10 w-[67.812vw] rounded-[10px] border-[3px] border-white bg-[#009A35] py-2 text-center text-[5vw] font-semibold text-white md:w-[660px] md:py-2 md:text-[19.2px] md:hover:shadow-[0_0_15px_#fff]"
      >
        <p class="pointer-events-none">高一家長LINE@群組</p>
      </a>
    </div>
    <div class="w-full">
      <img src="../public/assets/Background2.jpeg" alt="" />
    </div>
  </div>
  <!-- 暑假作業 -->
  <div id="homework" class="flex w-full flex-col items-center bg-[#e8c541]">
    <div class="w-[59.275vw] md:w-[288px]">
      <img
        src="../public/assets/Summer-homework-for-freshmen.png"
        class=""
        alt="新生暑假作業"
      />
    </div>
    <div
      class="flex w-full flex-col items-center space-y-[29.29px] py-4 md:flex-row md:justify-evenly md:space-y-0"
    >
      <a
        :href="datas[2].details[0].link"
        target="_blank"
        class="flex w-[31.25vw] items-center justify-center md:w-[120px] md:hover:scale-110"
      >
        <img src="../public/assets/book1.png" class="" alt="作業說明" />
      </a>
      <a
        :href="datas[2].details[1].link"
        target="_blank"
        class="flex w-[31.25vw] items-center justify-center md:w-[120px] md:hover:scale-110"
      >
        <img src="../public/assets/book2.png" class="" alt="暑假作業" />
      </a>
      <a
        :href="datas[2].details[2].link"
        target="_blank"
        class="flex w-[31.25vw] items-center justify-center md:w-[120px] md:hover:scale-110"
      >
        <img src="../public/assets/book3.png" class="" alt="銜接教材" />
      </a>
    </div>
    <div class="w-full">
      <img src="../public/assets/Background3.jpeg" class="" id="" />
    </div>
  </div>
  <!-- 應辦事項 -->
  <div
    id="matters"
    class="relative flex w-full flex-col items-center bg-[#34559D] py-5"
  >
    <div class="w-[81.25vw] md:w-[312px]">
      <img
        src="../public/assets/Freshmen-should-do.png"
        class="w-full"
        alt=""
      />
    </div>
    <div class="h-8"></div>
    <div
      class="grid grid-cols-1 justify-center gap-y-8 md:grid-flow-col md:grid-rows-3 lg:grid-rows-2"
    >
      <div class="w-[71.875vw] md:row-span-1 md:w-[276px]">
        <div class="relative">
          <div
            class="absolute left-[10px] top-[10px] h-[25vw] w-[62.5vw] bg-[#E8C541] md:h-[96px] md:w-[240px]"
          ></div>
          <div
            class="absolute flex h-[25vw] w-[62.5vw] items-center justify-center border-2 border-black bg-white text-center text-[6.25vw] font-bold md:h-[96px] md:w-[240px] md:text-[24px] md:leading-[28.8px]"
          >
            <p>線上訂購校服<br />(超商繳費)</p>
          </div>
        </div>
        <div class="h-[30vw] md:h-[115px]"></div>
        <ul
          class="mt-5 flex list-disc flex-col gap-y-3 pl-7 text-[5vw] font-semibold text-white md:text-[19.2px] md:leading-[28.8px]"
        >
          <a
            :href="matter.link"
            :key="matter.id"
            target="_blank"
            v-for="matter in datas[3].details[0]"
          >
            <li v-html="matter.title" class="md:hover:text-[20px]"></li>
          </a>
        </ul>
      </div>
      <div class="w-[71.875vw] md:row-span-2 md:w-[276px] lg:order-last">
        <div class="relative">
          <div
            class="absolute left-[10px] top-[10px] h-[25vw] w-[62.5vw] bg-[#E8C541] md:h-[96px] md:w-[240px]"
          ></div>
          <div
            class="absolute flex h-[25vw] w-[62.5vw] items-center justify-center border-2 border-black bg-white text-center text-[6.25vw] font-bold md:h-[96px] md:w-[240px] md:text-[24px] md:leading-[28.8px]"
          >
            <p>校務系統<br />新生填寫資料</p>
          </div>
        </div>
        <div class="h-[30vw] md:h-[115px]"></div>
        <ul
          class="mt-5 flex list-disc flex-col gap-y-3 pl-7 text-[5vw] font-semibold text-white md:text-[19.2px] md:leading-[28.8px]"
        >
          <a
            :href="matter.link"
            :key="matter.id"
            target="_blank"
            v-for="matter in datas[3].details[1]"
          >
            <li v-html="matter.title" class="md:hover:text-[20px]"></li>
          </a>
        </ul>
      </div>
      <div class="w-[71.875vw] md:row-span-1 md:w-[276px]">
        <div class="relative">
          <div
            class="absolute left-[10px] top-[10px] h-[25vw] w-[62.5vw] bg-[#E8C541] md:h-[96px] md:w-[240px]"
          ></div>
          <div
            class="absolute flex h-[25vw] w-[62.5vw] items-center justify-center border-2 border-black bg-white text-center text-[6.25vw] font-bold md:h-[96px] md:w-[240px] md:text-[24px] md:leading-[28.8px]"
          >
            <p>學雜費減免申請<br />(選辦)</p>
          </div>
        </div>
        <div class="h-[30vw] md:h-[115px]"></div>
        <ul
          class="mt-5 flex list-disc flex-col gap-y-3 pl-7 text-[5vw] font-semibold text-white md:text-[19.2px] md:leading-[28.8px]"
        >
          <a
            :href="matter.link"
            :key="matter.id"
            target="_blank"
            v-for="matter in datas[3].details[2]"
          >
            <li v-html="matter.title" class="md:hover:text-[20px]"></li>
          </a>
        </ul>
      </div>
      <div class="w-[71.875vw] md:row-span-1 md:w-[276px]">
        <div class="relative">
          <div
            class="absolute left-[10px] top-[10px] h-[25vw] w-[62.5vw] bg-[#E8C541] md:h-[96px] md:w-[240px]"
          ></div>
          <div
            class="absolute flex h-[25vw] w-[62.5vw] items-center justify-center border-2 border-black bg-white text-center text-[6.25vw] font-bold md:h-[96px] md:w-[240px] md:text-[24px] md:leading-[28.8px]"
          >
            <p>就學貸款申請<br />(選辦)</p>
          </div>
        </div>
        <div class="h-[30vw] md:h-[115px]"></div>
        <ul
          class="mt-5 flex list-disc flex-col gap-y-3 pl-7 text-[5vw] font-semibold text-white md:text-[19.2px] md:leading-[28.8px]"
        >
          <a
            :href="matter.link"
            :key="matter.id"
            target="_blank"
            v-for="matter in datas[3].details[3]"
          >
            <li v-html="matter.title" class="md:hover:text-[20px]"></li>
          </a>
        </ul>
      </div>
      <div
        class="w-[71.875vw] md:row-span-1 md:w-[276px] md:-translate-y-[50px] lg:translate-y-[0px]"
      >
        <div class="relative">
          <div
            class="absolute left-[10px] top-[10px] h-[25vw] w-[62.5vw] bg-[#E8C541] md:h-[96px] md:w-[240px]"
          ></div>
          <div
            class="absolute flex h-[25vw] w-[62.5vw] items-center justify-center border-2 border-black bg-white text-center text-[6.25vw] font-bold md:h-[96px] md:w-[240px] md:text-[24px] md:leading-[28.8px]"
          >
            <p>學生住宿申請<br />(選辦)</p>
          </div>
        </div>
        <div class="h-[30vw] md:h-[115px]"></div>
        <ul
          class="mt-5 flex list-disc flex-col gap-y-3 pl-7 text-[5vw] font-semibold text-white md:text-[19.2px] md:leading-[28.8px]"
        >
          <a
            :href="matter.link"
            :key="matter.id"
            target="_blank"
            v-for="matter in datas[3].details[4]"
          >
            <li v-html="matter.title" class="md:hover:text-[20px]"></li>
          </a>
        </ul>
      </div>
    </div>
    <div class="w-full place-items-start pt-3 md:pt-0">
      <div class="w-[59.375vw] md:w-[288px]">
        <img src="../public/assets/boy.png" alt="" />
      </div>
    </div>
  </div>
  <!-- 到校日期 -->
  <div
    id="arrive-date"
    class="flex w-full flex-col items-center bg-[#E8C541] pt-[20px] pb-[50px]"
  >
    <div class="pointer-events-none w-[87.5vw] md:w-[336px]">
      <img src="../public/assets/date.png" alt="" class="w-full" />
    </div>
    <div class="h-[24px]"></div>
    <div
      class="grid grid-cols-1 gap-y-5 gap-x-10 text-[6.25vw] font-semibold text-white md:grid-cols-2 md:text-[24px] lg:grid-cols-3"
    >
      <a
        v-for="date in datas[4].details"
        :href="date.link"
        :key="date.id"
        :id="date.id"
        :class="{ _disabled: isdisabled }"
        class="flex h-[31.25vw] w-[68.75vw] flex-col items-center justify-center rounded-[10px] bg-[#EC6261] text-center md:h-[120px] md:w-[264px] md:leading-[28.8px] md:hover:border-[5px] md:hover:border-white"
      >
        <p v-html="date.title"></p>
        <p v-html="date.title2"></p>
        <p v-html="date.time"></p>
      </a>
    </div>
  </div>
  <!-- 宣導事項 -->
  <div
    id="publicity"
    class="flex w-full flex-col items-center bg-[#34559D] pt-[10px]"
  >
    <div class="pointer-events-none w-[84.375vw] md:w-[324px]">
      <img src="../public/assets/Publicity-matters.png" alt="" class="w-full" />
    </div>
    <div class="h-[26px]"></div>
    <div
      class="grid grid-cols-2 gap-x-[4.687vw] gap-y-[25vw] md:grid-cols-3 md:gap-x-[18px] md:gap-y-[81px] lg:grid-cols-4"
    >
      <a
        v-for="pub in datas[5].details"
        target="_blank"
        :href="pub.link"
        :key="pub.id"
        class="group w-[42.187vw] text-center md:w-[221px] md:hover:w-[206px] md:hover:scale-110"
      >
        <div class="relative">
          <div
            class="absolute top-[10px] right-0 h-[12.5vw] w-[40.625vw] rounded-full bg-[#E8C541] md:h-[48px] md:w-[200px] md:group-hover:shadow-[0_0_15px_#fff]"
          ></div>
          <div
            class="absolute left-0 top-0 flex h-[12.5vw] w-[40.625vw] items-center justify-center rounded-full bg-white md:h-[48px] md:w-[200px]"
          >
            <p
              v-html="pub.title"
              class="text-[3.75vw] font-bold leading-[4.5vw] md:text-[14.4px] md:leading-[17.3px] md:group-hover:text-[17px]"
            ></p>
          </div>
        </div>
      </a>
    </div>
    <div class="h-[14vw]"></div>
    <div class="w-full">
      <img src="../public/assets/Background4.png" alt="" class="w-full" />
    </div>
  </div>
  <!-- 學校簡介 -->
  <div id="profile" class="flex w-full flex-col items-center bg-[#EC6261]">
    <div class="flex w-[50vw] items-center justify-center md:w-[192px]">
      <img src="../public/assets/School-Profile.png" alt="學校簡介" />
    </div>
    <div
      class="item-center grid grid-cols-2 justify-center gap-5 px-[20px] py-5 lg:grid-cols-3"
    >
      <div class="flex flex-col items-center">
        <iframe
          class="peer w-[37.5vw] md:w-[288px]"
          width="640"
          src="https://www.youtube.com/embed/q5qYnNstpx4"
          title="校長提醒新生的五件事"
          frameborder="0"
          allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
          allowfullscreen
        ></iframe>
        <img
          src="../public/assets/Principal-room.png"
          class="w-[25vw] md:w-[96px] md:hover:w-[110px] md:peer-hover:w-[110px]"
          alt="校長室"
        />
      </div>
      <div class="flex flex-col items-center">
        <iframe
          class="peer w-[37.5vw] md:w-[288px]"
          width="640"
          src="https://www.youtube.com/embed/fh2W_gLNmLk"
          title="學務處介紹"
          frameborder="0"
          allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
          allowfullscreen
        ></iframe>
        <img
          src="../public/assets/Academic-Affairs-Office.png"
          class="w-[25vw] md:w-[96px] md:hover:w-[110px] md:peer-hover:w-[110px]"
          alt="學務處"
        />
      </div>
      <div class="flex flex-col items-center">
        <iframe
          class="peer w-[37.5vw] md:w-[288px]"
          width="640"
          src="https://www.youtube.com/embed/OIUsy9nOOMo"
          title="教務處介紹"
          frameborder="0"
          allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
          allowfullscreen
        ></iframe>
        <img
          src="../public/assets/Academic-Affairs-Office(1).png"
          class="w-[25vw] md:w-[96px] md:hover:w-[110px] md:peer-hover:w-[110px]"
          alt="教務處"
        />
      </div>
      <div class="flex flex-col items-center">
        <iframe
          class="peer w-[37.5vw] md:w-[288px]"
          width="640"
          src="https://www.youtube.com/embed/01ero8fms_4"
          title="110新生圖書館介紹"
          frameborder="0"
          allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
          allowfullscreen
        ></iframe>
        <img
          src="../public/assets/library.png"
          class="w-[25vw] md:w-[96px] md:hover:w-[110px] md:peer-hover:w-[110px]"
          alt="圖書館"
        />
      </div>
      <div class="flex flex-col items-center">
        <iframe
          class="peer w-[37.5vw] md:w-[288px]"
          width="640"
          src="https://www.youtube.com/embed/edvqAHzOGeg"
          title="110輔導室介紹 打開輔導的通關密語"
          frameborder="0"
          allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
          allowfullscreen
        ></iframe>
        <img
          src="../public/assets/Counseling-Room.png"
          class="w-[25vw] md:w-[96px] md:hover:w-[110px] md:peer-hover:w-[110px]"
          alt="輔導室"
        />
      </div>
      <div class="flex flex-col items-center">
        <iframe
          class="peer w-[37.5vw] md:w-[288px]"
          width="640"
          src="https://www.youtube.com/embed/cMlbD0RmBG0"
          title="110學年度新生 總務處介紹"
          frameborder="0"
          allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
          allowfullscreen
        ></iframe>
        <img
          src="../public/assets/General-Services.png"
          class="w-[25vw] md:w-[96px] md:hover:w-[110px] md:peer-hover:w-[110px]"
          alt="總務處"
        />
      </div>
    </div>
  </div>
  <!-- 製作名單 -->
  <div class="w-full bg-[#34559D]">
    <div
      class="flex flex-row content-center items-center justify-center text-white md:justify-evenly md:p-[28px]"
    >
      <div class="py-[18px] text-right text-[3.75vw] md:hidden">
        <p>
          DESIGNED BY<br />
          CREATED BY<br />
          MENTORED BY<br />
          POWERED BY
        </p>
      </div>
      <div class="px-2 text-left text-[3.75vw] md:hidden">
        <p>
          白宜巧 呂昱萱<br />
          林怡均 黃冠霖<br />
          陳晉<br />
          FHSH IT DEPT
        </p>
      </div>
      <div class="hidden flex-row space-x-5 md:flex">
        <div class="text-right">
          <p class="">DESIGNED BY</p>
          <p class="">CREATED BY</p>
        </div>
        <div class="text-left">
          <p class="">白宜巧 呂昱萱</p>
          <p class="">林怡均 黃冠霖</p>
        </div>
      </div>
      <div class="hidden flex-row space-x-5 md:flex">
        <div class="text-right">
          <p class="">MENTORED BY</p>
          <p class="">POWERED BY</p>
        </div>
        <div class="text-left">
          <p class="">陳晉</p>
          <p class="">FHSH IT DEPT</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
function closeModel() {
  document.getElementById("model").classList.add("hidden");
}

function jumpFuntion() {
  document.getElementById("jump").classList.toggle("-translate-x-[62.5vw]");
}

document.onclick = function (e) {
  if (e.target.id !== "jump" && e.target.id !== "list-button") {
    document.getElementById("jump").classList.add("-translate-x-[62.5vw]");
  }
};
import { ref, reactive } from "vue";
export default {
  setup() {
    const close = function () {
      closeModel();
    };
    const jump = function () {
      jumpFuntion();
    };
    const isdisabled = ref(false);
    const datas = reactive([
      {
        index: 0,
        title: "新生線上報到",
        details: [
          {
            link: "",
            id: "c1",
            title:
              "普通班免試<br>新生線上報到<br><span class='text-[5vw] md:text-[20px]'>(優免/安置上傳畢業證書)</span>",
            time: "7月19日11:00<br>~7月21日11:00",
            announceTime: new Date("2022-07-19T11:00:00+08:00").getTime(),
            expiredTime: new Date("2022-07-21T11:00:00+08:00").getTime(),
          },
          {
            link: "",
            id: "c2",
            title: "體育班<br>新生上傳畢業證書",
            time: "7月19日11:00<br>~7月21日12:00",
            announceTime: new Date("2022-07-19T11:00:00+08:00").getTime(),
            expiredTime: new Date("2022-07-21T12:00:00+08:00").getTime(),
          },
          {
            link: "",
            id: "c3",
            title: "戲劇班<br>正取生線上報到",
            time: "7月19日09:00<br>~7月20日12:00",
            title2: "備取生線上報到",
            time2: "7月20日17:00<br>~7月21日12:00",
          },
          {
            link: "",
            id: "c4",
            title: "音樂班<br>新生線上報到",
            time: "7月19日11:00<br>~7月20日12:00",
          },
          {
            link: "",
            id: "c5",
            title:
              "美術班<br>新生線上報到<br><span class='text-[5vw] md:text-[20px]'>(已經上傳畢業證書)</span>",
            time: "7月19日11:00<br>~7月20日12:00",
          },
          {
            link: "",
            id: "c6",
            title: "舞蹈班<br>新生線上報到",
            time: "7月19日11:00<br>~7月20日12:00",
          },
        ],
      },
      {
        index: 1,
        title: "學校簡介",
        details: [
          {
            title: "復興高中111學年度新生行事曆暨檢核表(新生與家長必看)",
            link: "https://drive.google.com/file/d/1a2IODRsigIexcUrYrinGcLhsrn7LC4ql/view?usp=sharing",
            announceTime: null,
            expiredTime: null,
          },
          {
            title: "選課輔導手冊(普通班)",
            link: "",
            announceTime: null,
            expiredTime: null,
          },
          {
            title: "學校簡報1",
            link: "https://drive.google.com/file/d/1Dgj6tUN1JNS22Dc6OIrYsD9JQH3IYNQM/preview",
          },
          {},
          {},
          {},
          {},
        ],
      },
      {
        index: 2,
        title: "新生暑假作業",
        details: [
          {
            title: "111學年度高一新生暑假作業說明(開學第一週交給任課老師)",
            link: "https://drive.google.com/file/d/1FhXRCiuQYCqAGAbyEPuPbKbHiHdEOiI5/view?usp=sharing",
            announceTime: null,
            expiredTime: null,
          },
          {
            title: "高一數學銜接教材~復興高中新生暑假作業版(請列印演練第1~8頁)",
            link: "https://drive.google.com/file/d/1XbUCOZdblxAbRERT6ErD42F2XkM_TVJT/view?usp=sharing",
            announceTime: null,
            expiredTime: null,
          },
          {
            title:
              "高一數學銜接教材~龍騰出版社9單元51頁完整版(歡迎參考_免寫免交)",
            link: "https://drive.google.com/file/d/1y6thma_fMuk6Y5j60laz3jzlkpeTVrTm/view?usp=sharing",
            announceTime: null,
            expiredTime: null,
          },
        ],
      },
      {
        index: 3,
        title: "新生應辦及選辦事項",
        details: [
          [
            {
              link: "",
              id: "m1-1",
              title: "新生線上訂購校服<br>(7/21鏈結校務系統)",
            },
            {
              link: "",
              id: "m1-2",
              title: "新生線上訂購校服流程說明",
            },
            {
              link: "",
              id: "m1-3",
              title: "復興新生校服介紹",
            },
          ],
          [
            {
              link: "",
              id: "m2-1",
              title: "新生填寫資料<br>(7/21鏈結校務系統)",
            },
            {
              link: "",
              id: "m2-2",
              title: "校務系統新生填寫應備<br>資料說明",
            },
            {
              link: "",
              id: "m2-3",
              title: "校務系統高一多元選修<br>選課說明",
            },
            {
              link: "",
              id: "m2-4",
              title: "學生受款帳戶登記說明",
            },
            {
              link: "",
              id: "m2-5",
              title: "教育部12年國教<br>免學費補助查調說明",
            },
            {
              link: "",
              id: "m2-6",
              title: "數位學生證整合服務說明",
            },
          ],
          [
            {
              link: "",
              id: "m3-1",
              title: "學生住宿申請鏈結表單",
            },
            {
              link: "",
              id: "m3-2",
              title: "學雜費減免申請說明",
            },
          ],

          [
            {
              link: "",
              id: "m4-1",
              title: "就學貸款申請鏈結表單",
            },
            {
              link: "",
              id: "m4-2",
              title: "就學貸款申請說明",
            },
          ],
          [
            {
              link: "",
              id: "m5-1",
              title: "學生住宿申請鏈結表單",
            },
            {
              link: "",
              id: "m5-2",
              title: "學生住宿申請說明",
            },
          ],
        ],
      },
      {
        index: 4,
        title: "新生實體到校日期",
        details: [
          {
            link: "",
            id: "d1",
            title: "高一編班座號學號",
            time: "(8/19公告)",
          },
          {
            link: "",
            id: "d2",
            title: "新生住宿名單",
            time: "(8/19 16:00公告)",
          },
          {
            link: "",
            id: "d3",
            title: "新生始業輔導",
            title2: "實施計畫",
            time: "(8/16公告)",
          },
          {
            link: "",
            id: "d4",
            title: "新生始業輔導手冊",
            time: "(8/23公告)",
          },
          {
            link: "",
            id: "d5",
            title: "開學日實施計畫",
            time: "(8/23公告)",
          },
          {
            link: "",
            id: "d6",
            title: "學生開學日",
            title2: "領取教科書",
            time: "(8/23公告)",
          },
          {
            link: "",
            id: "d7",
            title: "新生開學日",
            title2: "領取校服",
            time: "(8/23公告)",
          },
          {
            link: "",
            id: "d8",
            title: "110-1學期行事曆",
            time: "(8/24公告)",
          },
          {
            link: "",
            id: "d9",
            title: "學生信箱與",
            title2: "單一身分帳號",
            time: "(8/23公告)",
          },
          {
            link: "",
            id: "d10",
            title: "學生家長",
            title2: "校務行政系統說明",
            time: "(8/23公告)",
          },
          {
            link: "",
            id: "d11",
            title: "校園繳費系統",
            title2: "親子身分綁定",
            time: "(8/23公告)",
          },
        ],
      },
      {
        index: 5,
        title: "新生其他宣導事項",
        details: [
          {
            link: "",
            id: "p1",
            title: "語文競賽增額報名<br>(教學組)",
          },
          {
            link: "",
            id: "p2",
            title: "學科增能<br>(實研組)",
          },
          {
            link: "",
            id: "p3",
            title: "彈性學習說明<br>(實研組)",
          },
          {
            link: "",
            id: "p4",
            title: "跑班課程說明<br>(實研組)",
          },
          {
            link: "",
            id: "p5",
            title: "臺英學士培育計畫<br>(實研組)",
          },
          {
            link: "",
            id: "p6",
            title: "圖書館介紹<br>(圖書館)",
          },
          {
            link: "",
            id: "p7",
            title: "圖書館推廣活動<br>(圖書館)",
          },
          {
            link: "",
            id: "p8",
            title: "自主學習規範<br>(圖書館)",
          },
          {
            link: "",
            id: "p9",
            title: "志工、工讀生招募<br>(圖書館)",
          },
          {
            link: "",
            id: "p10",
            title: "社團一覽表<br>(訓育組)",
          },
          {
            link: "",
            id: "p11",
            title: "獎學金(註冊組)<br>就學扶助(生輔組)",
          },
          {
            link: "",
            id: "p12",
            title: "111學生家長手冊<br>(生輔組)",
          },
          {
            link: "",
            id: "p13",
            title: "輔導室介紹<br>(輔導室)",
          },
          {
            link: "",
            id: "p14",
            title: "學生學習歷程檔案<br>(輔導室)",
          },
          {
            link: "",
            id: "p15",
            title: "學習評量相關規定<br>(註冊組)",
          },
          {
            link: "",
            id: "p16",
            title: "合作社介紹<br>(合作社)",
          },
          {
            link: "",
            id: "p17",
            title: "教室位置平面圖<br>(設備組)",
          },
          {
            link: "",
            id: "p18",
            title: "交通圖、接駁車<br>(生輔組)",
          },
        ],
      },
      {
        index: 6,
        title: "選單",
        details: [
          {
            link: "#timeline",
            id: "l1",
            title: "新生入學時程表",
          },
          {
            link: "#register",
            id: "l2",
            title: "新生線上報到",
          },
          {
            link: "#briefing",
            id: "l3",
            title: "入學說明簡報",
          },
          {
            link: "#line",
            id: "l4",
            title: "高一家長Line@群組",
          },
          {
            link: "#homework",
            id: "l5",
            title: "新生暑假作業",
          },
          {
            link: "#matters",
            id: "l6",
            title: "新生應辦及選辦事項",
          },
          {
            link: "#arrive-date",
            id: "l7",
            title: "新生實體到校日期",
          },
          {
            link: "#publicity",
            id: "l8",
            title: "新生其他宣導事項",
          },
          {
            link: "#profile",
            id: "l9",
            title: "學校簡介",
          },
        ],
      },
    ]);
    const timecheck = function (i) {
      datas[i].details.filter((x) => {
        if (x.announceTime > Date.now() || x.expiredTime < Date.now()) {
          return (isdisabled.value = true);
        } else {
          return (isdisabled.value = false);
        }
      });
    };
    const url = "https://freshman-api.fhsh.tp.edu.tw/api/v1/fresh-datas";
    fetch(url)
      .then((response) => {
        return response.json();
      })
      .then((jsonData) => {
        for (var i = 0; i < 6; i++) {
          if (jsonData.datas[i].details.length !== 0) {
            datas[i].details = jsonData.datas[i].details;
          }
          // not working
          // datas[i].details.filter((x) => {
          //   if (x.announceTime < Date.now() && x.expiredTime > Date.now()) {
          //     isdisabled.value = false;
          //   } else if (x.announceTime < Date.now()) {
          //     isdisabled.value = false;
          //   } else {
          //     isdisabled.value = true;
          //   }
          // });
        }

        // datas[4].details.forEach((x) => if(x.announceTime));
      })
      .catch((err) => {
        console.log(err);
      });

    return {
      close,
      jump,
      datas,
      isdisabled,
      timecheck,
    };
  },
};
</script>
