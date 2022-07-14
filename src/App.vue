<template>
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
    class="fixed z-50 flex w-[62.5vw] -translate-x-[62.5vw] flex-col items-center bg-[#34559D] p-[18px] duration-200 md:w-[240px]"
  >
    <div class="pointer-events-none w-[37.5vw] md:w-[144px]">
      <img src="/assets/Freshmen-area-content.PNG" alt="" />
    </div>
    <div class="h-[15px]"></div>
    <ul
      class="w-[48.125vw] text-[3.75vw] font-semibold text-white md:w-[184.8px] md:text-[14.4px]"
    >
      <li>
        <a
          v-for="list in datas.lists"
          :href="list.href"
          :key="list.id"
          class="mb-2 flex h-[10vw] items-center justify-center rounded-[5px] bg-[#EC6261] md:h-[38.4px]"
          >{{ list.name }}
        </a>
      </li>
    </ul>
  </div>
  <!-- 封面 -->
  <div id="header" class="w-full">
    <img src="/assets/phone.jpeg" alt="" class="md:hidden" />
    <img src="/assets/computer.jpeg" alt="" />
  </div>
  <!-- 時程表 -->
  <div id="timeline" class="flex w-full flex-col items-center justify-center">
    <div class="w-[59.375vw] md:w-[228px]">
      <img
        src="/assets/Freshman-Admission-Schedule.png"
        class=""
        alt="新生入學時程表"
      />
    </div>
    <div
      class="flex w-full place-items-center items-center justify-center md:w-[500px]"
    >
      <img src="/assets/timeline-phone.png" class="md:hidden" alt="時程表" />
      <img src="/assets/Timeline.png" class="hidden md:flex" alt="" />
    </div>
    <div class="w-full">
      <img src="/assets/Background1.jpeg" alt="" />
    </div>
  </div>
  <!-- 新生報到 -->
  <div id="register" class="flex w-full flex-col items-center bg-[#EC6261]">
    <div class="w-[59.375vw] md:w-[228px]">
      <img src="/assets/Online-registration-for-new-students.png" alt="" />
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
        v-for="check in datas.checks"
        :href="check.href"
        :key="check.id"
        class="flex h-[62.5vw] w-[62.5vw] flex-col items-center justify-center rounded-[20px] bg-[#34559D] text-center text-[6.25vw] font-semibold leading-[7vw] hover:border-[5px] hover:border-white md:h-[240px] md:w-[240px] md:text-[24px] md:leading-[28.8px]"
      >
        <p class="pointer-events-none text-white" v-html="check.name"></p>
        <p class="pointer-events-none text-[#EC6261]" v-html="check.time"></p>
        <p class="pointer-events-none text-white" v-html="check.name2"></p>
        <p class="pointer-events-none text-[#EC6261]" v-html="check.time2"></p>
      </a>
    </div>
    <div class="h-5 md:h-10"></div>
    <div>
      <a
        href=""
        class="flex h-[15.625vw] w-[87.5vw] items-center justify-center rounded-xl bg-[#E8C541] text-[6.25vw] font-semibold text-white hover:border-[5px] hover:border-white md:h-[60px] md:w-[336px] md:text-[24px]"
      >
        <p>選課輔導手冊(普通班)</p>
      </a>
    </div>
    <div class="h-7 md:h-14"></div>
  </div>
  <!-- 說明簡報 -->
  <div
    id="briefing"
    class="relative flex w-full flex-col items-center bg-[#EC6261] pt-3"
  >
    <div class="w-[59.375vw] md:w-[228px]">
      <img src="/assets/Admissions-Briefing.png" alt="" />
    </div>
    <div class="h-8"></div>
    <iframe
      class="h-[51.953vw] w-[78.125vw] md:h-[400px] md:w-[600px]"
      src="https://drive.google.com/file/d/1Dgj6tUN1JNS22Dc6OIrYsD9JQH3IYNQM/preview"
      allow="autoplay"
    ></iframe>
    <div
      class="absolute left-0 bottom-28 w-[28.125vw] md:w-[216px] lg:left-16 lg:bottom-52"
    >
      <img src="/assets/girl.PNG" alt="" />
    </div>
    <div class="h-20 md:h-10"></div>
    <div class="flex w-full items-center justify-center bg-[#EC6261]">
      <a
        href=""
        id="line"
        class="z-10 w-[67.812vw] rounded-[10px] border-[3px] border-white bg-[#009A35] py-2 text-center text-[5vw] font-semibold text-white hover:shadow-[0_0_15px_#fff] md:w-[660px] md:py-2 md:text-[19.2px]"
      >
        <p class="pointer-events-none">高一家長LINE@群組</p>
      </a>
    </div>
    <div class="w-full">
      <img src="/assets/Background2.jpeg" alt="" />
    </div>
  </div>
  <!-- 暑假作業 -->
  <div id="homework" class="flex w-full flex-col items-center bg-[#e8c541]">
    <div class="w-[59.275vw] md:w-[288px]">
      <img
        src="/assets/Summer-homework-for-freshmen.png"
        class=""
        alt="新生暑假作業"
      />
    </div>
    <div
      class="flex w-full flex-col items-center space-y-[29.29px] py-4 md:flex-row md:justify-evenly"
    >
      <a href="" class="w-[31.25vw] md:w-[120px]">
        <img src="/assets/book1.png" class="py-4" alt="作業說明" />
      </a>
      <a href="" class="w-[31.25vw] md:w-[120px]">
        <img src="/assets/book2.png" class="py-4" alt="暑假作業" />
      </a>
      <a href="" class="w-[31.25vw] md:w-[120px]">
        <img src="/assets/book3.png" class="py-4" alt="銜接教材" />
      </a>
    </div>
    <div class="w-full">
      <img src="/assets/Background3.jpeg" class="" id="" />
    </div>
  </div>
  <!-- 應辦事項 -->
  <div
    id="matters"
    class="relative flex w-full flex-col items-center bg-[#34559D] py-5"
  >
    <div class="w-[81.25vw] md:w-[312px]">
      <img src="/assets/Freshmen-should-do.png" class="w-full" alt="" />
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
            <p>學雜費減免申請<br />(選辦)</p>
          </div>
        </div>
        <div class="h-[30vw] md:h-[115px]"></div>
        <ul
          class="mt-5 flex list-disc flex-col gap-y-3 pl-7 text-[5vw] font-semibold text-white md:text-[19.2px] md:leading-[28.8px]"
        >
          <a
            :href="matter.href"
            :key="matter.id"
            v-for="matter in datas.matters1"
          >
            <li v-html="matter.name" class="hover:text-[20px]"></li>
          </a>
        </ul>
      </div>
      <div
        class="w-[71.875vw] md:row-span-1 md:w-[276px] md:-translate-y-[50px]"
      >
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
            :href="matter.href"
            :key="matter.id"
            v-for="matter in datas.matters2"
          >
            <li v-html="matter.name" class="hover:text-[20px]"></li>
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
            :href="matter.href"
            :key="matter.id"
            v-for="matter in datas.matters3"
          >
            <li v-html="matter.name" class="hover:text-[20px]"></li>
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
            :href="matter.href"
            :key="matter.id"
            v-for="matter in datas.matters4"
          >
            <li v-html="matter.name" class="hover:text-[20px]"></li>
          </a>
        </ul>
      </div>
      <div
        class="w-[71.875vw] md:row-span-1 md:w-[276px] lg:-translate-y-[50px]"
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
            :href="matter.href"
            :key="matter.id"
            v-for="matter in datas.matters5"
          >
            <li v-html="matter.name" class="hover:text-[20px]"></li>
          </a>
        </ul>
      </div>
    </div>
    <div class="w-full place-items-start pt-3 md:pt-0">
      <div class="w-[59.375vw] md:w-[288px]">
        <img src="/assets/boy.PNG" alt="" />
      </div>
    </div>
  </div>
  <!-- 到校日期 -->
  <div
    id="arrive-date"
    class="flex w-full flex-col items-center bg-[#E8C541] pt-[20px] pb-[50px]"
  >
    <div class="pointer-events-none w-[87.5vw] md:w-[336px]">
      <img src="/assets/date.png" alt="" class="w-full" />
    </div>
    <div class="h-[24px]"></div>
    <div
      class="grid grid-cols-1 gap-y-5 gap-x-10 text-[6.25vw] font-semibold text-white md:grid-cols-2 md:text-[24px] lg:grid-cols-3"
    >
      <a
        v-for="date in datas.dates"
        :href="date.href"
        :key="date.id"
        class="flex h-[31.25vw] w-[68.75vw] items-center justify-center rounded-[10px] bg-[#EC6261] text-center hover:border-[5px] hover:border-white md:h-[120px] md:w-[264px] md:leading-[28.8px]"
      >
        {{ date.name }}<br />{{ date.name2 }}<br />{{ date.time }}
      </a>
    </div>
  </div>
  <!-- 宣導事項 -->
  <div
    id="publicity"
    class="flex w-full flex-col items-center bg-[#34559D] pt-[10px]"
  >
    <div class="pointer-events-none w-[84.375vw] md:w-[324px]">
      <img src="/assets/Publicity-matters.png" alt="" class="w-full" />
    </div>
    <div class="h-[26px]"></div>
    <div
      class="grid grid-cols-2 gap-x-[4.687vw] gap-y-[25vw] md:grid-cols-3 md:gap-x-[18px] md:gap-y-[81px] lg:grid-cols-5"
    >
      <a
        v-for="pub in datas.pubs"
        :href="pub.href"
        :key="pub.id"
        class="group w-[42.187vw] text-center hover:w-[165px] md:w-[162px]"
      >
        <div class="relative">
          <div
            class="absolute top-[10px] right-0 h-[12.5vw] w-[40.625vw] rounded-full bg-[#E8C541] group-hover:shadow-[0_0_15px_#fff] md:h-[48px] md:w-[156px]"
          ></div>
          <div
            class="absolute left-0 top-0 flex h-[12.5vw] w-[40.625vw] items-center justify-center rounded-full bg-white md:h-[48px] md:w-[156px]"
          >
            <p
              v-html="pub.name"
              class="text-[3.75vw] font-bold leading-[4.5vw] group-hover:text-[17px] md:text-[14.4px] md:leading-[17.3px]"
            ></p>
          </div>
        </div>
      </a>
    </div>
    <div class="h-[14vw]"></div>
    <div class="w-full">
      <img src="/assets/Background4.png" alt="" class="w-full" />
    </div>
  </div>
  <!-- 學校簡介 -->
  <div id="profile" class="flex w-full flex-col items-center bg-[#EC6261]">
    <div class="flex w-[50vw] items-center justify-center md:w-[192px]">
      <img src="/assets/School-Profile.PNG" alt="學校簡介" />
    </div>
    <div
      class="item-center grid grid-cols-2 justify-center gap-5 px-[20px] py-5 lg:grid-cols-3"
    >
      <div class="flex flex-col items-center">
        <iframe
          class="peer w-[37.5vw] md:w-[288px]"
          width="640"
          src="https://www.youtube.com/embed/goL1TnVES0M"
          title="臺北市立復興高級中學自主學習尋夢計畫"
          frameborder="0"
          allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
          allowfullscreen
        ></iframe>
        <img
          src="/assets/Principal-room.png"
          class="w-[25vw] hover:w-[110px] peer-hover:w-[110px] md:w-[96px]"
          alt="校長室"
        />
      </div>
      <div class="flex flex-col items-center">
        <iframe
          class="peer w-[37.5vw] md:w-[288px]"
          width="640"
          src="https://www.youtube.com/embed/goL1TnVES0M"
          title="臺北市立復興高級中學自主學習尋夢計畫"
          frameborder="0"
          allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
          allowfullscreen
        ></iframe>
        <img
          src="/assets/Academic-Affairs-Office.png"
          class="w-[25vw] hover:w-[110px] peer-hover:w-[110px] md:w-[96px]"
          alt="教務處"
        />
      </div>
      <div class="flex flex-col items-center">
        <iframe
          class="peer w-[37.5vw] md:w-[288px]"
          width="640"
          src="https://www.youtube.com/embed/goL1TnVES0M"
          title="臺北市立復興高級中學自主學習尋夢計畫"
          frameborder="0"
          allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
          allowfullscreen
        ></iframe>
        <img
          src="/assets/Academic-Affairs-Office(1).png"
          class="w-[25vw] hover:w-[110px] peer-hover:w-[110px] md:w-[96px]"
          alt="學務處"
        />
      </div>
      <div class="flex flex-col items-center">
        <iframe
          class="peer w-[37.5vw] md:w-[288px]"
          width="640"
          src="https://www.youtube.com/embed/goL1TnVES0M"
          title="臺北市立復興高級中學自主學習尋夢計畫"
          frameborder="0"
          allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
          allowfullscreen
        ></iframe>
        <img
          src="/assets/library.png"
          class="w-[25vw] hover:w-[110px] peer-hover:w-[110px] md:w-[96px]"
          alt="圖書館"
        />
      </div>
      <div class="flex flex-col items-center">
        <iframe
          class="peer w-[37.5vw] md:w-[288px]"
          width="640"
          src="https://www.youtube.com/embed/goL1TnVES0M"
          title="臺北市立復興高級中學自主學習尋夢計畫"
          frameborder="0"
          allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
          allowfullscreen
        ></iframe>
        <img
          src="/assets/Counseling-Room.png"
          class="w-[25vw] hover:w-[110px] peer-hover:w-[110px] md:w-[96px]"
          alt="輔導室"
        />
      </div>
      <div class="flex flex-col items-center">
        <iframe
          class="peer w-[37.5vw] md:w-[288px]"
          width="640"
          src="https://www.youtube.com/embed/goL1TnVES0M"
          title="臺北市立復興高級中學自主學習尋夢計畫"
          frameborder="0"
          allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
          allowfullscreen
        ></iframe>
        <img
          src="/assets/General-Services.png"
          class="w-[25vw] hover:w-[110px] peer-hover:w-[110px] md:w-[96px]"
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
function jumpFuntion() {
  document.getElementById("jump").classList.toggle("-translate-x-[62.5vw]");
}

document.onclick = function (e) {
  if (e.target.id !== "jump" && e.target.id !== "list-button") {
    document.getElementById("jump").classList.add("-translate-x-[62.5vw]");
  }
};

import { reactive } from "vue";
export default {
  setup() {
    const jump = function () {
      jumpFuntion();
    };

    const fetchOption = {
      mode: "no-cors",
    };

    const url = "https://freshman-api.fhsh.tp.edu.tw/api/v1";
    fetch(url, fetchOption)
      .then((response) => {
        return response.json();
      })
      .then((jsonData) => {
        console.log(jsonData);
      })
      .catch((err) => {
        console.log(err);
      });

    const datas = reactive({
      lists: [
        {
          href: "#timeline",
          id: "l1",
          name: "新生入學時程表",
        },
        {
          href: "#register",
          id: "l2",
          name: "新生線上報到",
        },
        {
          href: "#briefing",
          id: "l3",
          name: "入學說明簡報",
        },
        {
          href: "#line",
          id: "l4",
          name: "高一家長Line@群組",
        },
        {
          href: "#homework",
          id: "l5",
          name: "新生暑假作業",
        },
        {
          href: "#matters",
          id: "l6",
          name: "新生應辦及選辦事項",
        },
        {
          href: "#arrive-date",
          id: "l7",
          name: "新生實體到校日期",
        },
        {
          href: "#publicity",
          id: "l8",
          name: "新生其他宣導事項",
        },
        {
          href: "#profile",
          id: "l9",
          name: "學校簡介",
        },
      ],
      checks: [
        {
          href: "#",
          id: "c1",
          name: "普通班免試<br>新生線上報到<br>(優免/安置上傳畢證)",
          time: "7月19日11:00<br>~7月21日11:00",
        },
        {
          href: "#",
          id: "c2",
          name: "體育班<br>新生上傳畢證",
          time: "7月19日11:00<br>~7月21日12:00",
        },
        {
          href: "#",
          id: "c3",
          name: "戲劇班<br>正取生線上報到",
          time: "7月19日09:00<br>~7月20日12:00",
          name2: "備取生線上報到",
          time2: "7月20日17:00<br>~7月21日12:00",
        },
        {
          href: "#",
          id: "c4",
          name: "音樂班<br>新生線上報到",
          time: "7月19日11:00<br>~7月20日12:00",
        },
        {
          href: "#",
          id: "c5",
          name: "美術班<br>新生線上報到<br>(已經上傳畢證)",
          time: "7月19日11:00<br>~7月20日12:00",
        },
        {
          href: "#",
          id: "c6",
          name: "舞蹈班<br>新生線上報到",
          time: "7月19日11:00<br>~7月20日11:00",
        },
      ],
      matters1: [
        {
          href: "",
          id: "m1-1",
          name: "學生住宿申請鏈結表單",
        },
        {
          href: "",
          id: "m1-2",
          name: "學雜費減免申請說明",
        },
      ],
      matters2: [
        {
          href: "",
          id: "m2-1",
          name: "新生線上訂購校服<br>(7/21鏈結飛宇系統)",
        },
        {
          href: "",
          id: "m2-2",
          name: "新生線上訂購校服流程說明",
        },
        {
          href: "",
          id: "m2-3",
          name: "復興新生校服介紹",
        },
      ],
      matters3: [
        {
          href: "",
          id: "m3-1",
          name: "就學貸款申請鏈結表單",
        },
        {
          href: "",
          id: "m3-2",
          name: "就學貸款申請說明",
        },
      ],
      matters4: [
        {
          href: "",
          id: "m4-1",
          name: "新生填寫資料<br>(7/21鏈結飛宇系統)",
        },
        {
          href: "",
          id: "m4-2",
          name: "校務系統新生填寫應備<br>資料說明",
        },
        {
          href: "",
          id: "m4-3",
          name: "校務系統高一多元選修<br>選課說明",
        },
        {
          href: "",
          id: "m4-4",
          name: "學生受款帳戶登記說明",
        },
        {
          href: "",
          id: "m4-5",
          name: "教育部12年國教<br>免學費補助查調說明",
        },
        {
          href: "",
          id: "m4-6",
          name: "數位學生證整合服務說明",
        },
      ],
      matters5: [
        {
          href: "",
          id: "m5-1",
          name: "學生住宿申請鏈結表單",
        },
        {
          href: "",
          id: "m5-2",
          name: "學生住宿申請說明",
        },
      ],
      dates: [
        {
          href: "#",
          id: "d1",
          name: "新生始業輔導",
          name2: "實施計畫",
          time: "(8/16公告)",
        },
        {
          href: "#",
          id: "d2",
          name: "高一編班座號學號",
          time: "(8/19公告)",
        },
        {
          href: "#",
          id: "d3",
          name: "新生住宿名單",
          time: "(8/19 16:00公告)",
        },
        {
          href: "#",
          id: "d4",
          name: "新生始業輔導手冊",
          time: "(8/23公告)",
        },
        {
          href: "#",
          id: "d5",
          name: "開學日實施計畫",
          time: "(8/23公告)",
        },
        {
          href: "#",
          id: "d6",
          name: "學生開學日",
          name2: "領取教科書",
          time: "(8/23公告)",
        },
        {
          href: "#",
          id: "d7",
          name: "新生開學日",
          name2: "領取校服",
          time: "(8/23公告)",
        },
        {
          href: "#",
          id: "d8",
          name: "學生信箱與",
          name2: "單一身分帳號",
          time: "(8/23公告)",
        },
        {
          href: "#",
          id: "d9",
          name: "學生家長",
          name2: "校務行政系統說明",
          time: "(8/23公告)",
        },
        {
          href: "#",
          id: "d10",
          name: "校園繳費系統",
          name2: "親子身分綁定",
          time: "(8/23公告)",
        },
        {
          href: "#",
          id: "d11",
          name: "110-1學期行事曆",
          time: "(8/24公告)",
        },
      ],
      pubs: [
        {
          href: "",
          id: "p1",
          name: "語文競賽增額報名<br>(教學組)",
        },
        {
          href: "",
          id: "p2",
          name: "學科增能<br>(實研組)",
        },
        {
          href: "",
          id: "p3",
          name: "彈性學習說明<br>(實研組)",
        },
        {
          href: "",
          id: "p4",
          name: "跑班課程說明<br>(實研組)",
        },
        {
          href: "",
          id: "p5",
          name: "臺英學士培育計畫<br>(實研組)",
        },
        {
          href: "",
          id: "p6",
          name: "圖書館介紹<br>(圖書館)",
        },
        {
          href: "",
          id: "p7",
          name: "圖書館推廣活動<br>(圖書館)",
        },
        {
          href: "",
          id: "p8",
          name: "自主學習規範<br>(圖書館)",
        },
        {
          href: "",
          id: "p9",
          name: "志工、工讀生招募<br>(圖書館)",
        },
        {
          href: "",
          id: "p10",
          name: "合作社介紹<br>(合作社)",
        },
        {
          href: "",
          id: "p11",
          name: "社團一覽表<br>(訓育組)",
        },
        {
          href: "",
          id: "p12",
          name: "獎學金<br>(註冊組)",
        },
        {
          href: "",
          id: "p13",
          name: "就學扶助<br>(生輔組)",
        },
        {
          href: "",
          id: "p14",
          name: "111學生家長手冊<br>(生輔組)",
        },
        {
          href: "",
          id: "p15",
          name: "學習評量相關規定<br>(註冊組)",
        },
        {
          href: "",
          id: "p16",
          name: "輔導室介紹<br>(輔導室)",
        },
        {
          href: "",
          id: "p17",
          name: "學生學習歷程檔案<br>(輔導室)",
        },
        {
          href: "",
          id: "p18",
          name: "教室位置平面圖<br>(設備組)",
        },
        {
          href: "",
          id: "p19",
          name: "交通圖、接駁車<br>(生輔組)",
        },
      ],
    });

    return {
      jump,
      datas,
    };
  },
};
</script>
