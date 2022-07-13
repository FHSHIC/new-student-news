<template>
  <!-- 選單 -->
  <div class="fixed top-0 z-40">
    <div
      @click="jump()"
      id="list-button"
      class="fixed flex h-[9.375vw] w-full cursor-pointer items-center justify-center bg-white/20 text-[3.75vw] font-semibold text-white"
    >
      <p class="pointer-events-none">快捷選單</p>
    </div>
  </div>
  <div
    id="jump"
    class="fixed z-50 flex w-[62.5vw] -translate-x-[62.5vw] flex-col items-center bg-[#34559D] p-[18px] duration-200"
  >
    <div class="pointer-events-none w-[37.5vw]">
      <img src="/assets/Freshmen-area-content.PNG" alt="" />
    </div>
    <div class="h-[15px]"></div>
    <ul class="w-[48.125vw] text-[3.75vw] font-semibold text-white">
      <li>
        <a
          v-for="list in datas.lists"
          :href="list.href"
          :key="list.id"
          class="mb-2 flex h-[10vw] items-center justify-center rounded-[5px] bg-[#EC6261]"
          >{{ list.name }}
        </a>
      </li>
    </ul>
  </div>
  <!-- 新生報到 -->
  <div id="register" class="flex w-full flex-col items-center bg-[#EC6261]">
    <div class="w-[59.375vw]">
      <img src="/assets/Online-registration-for-new-students.png" alt="" />
    </div>
    <div class="flex flex-col items-center space-y-[12px]">
      <p class="text-[6.25vw] font-semibold text-[#34559D]">
        !!!新生請先線上報到!!!
      </p>
      <p class="text-[4.687vw] font-semibold text-white">
        (1)查詢錄取名單(報到編號)<br />(2)線上報到、上傳畢證、本土語文選課
      </p>
      <p class="text-center text-[6.25vw] font-semibold text-[#34559D]">
        逾期未報到<br />
        視同放棄錄取資格
      </p>
    </div>
    <div class="mt-5 grid grid-cols-1 items-center justify-center gap-5">
      <a
        v-for="check in datas.checks"
        :href="check.href"
        :key="check.id"
        class="flex h-[62.5vw] w-[62.5vw] flex-col items-center justify-center rounded-[20px] bg-[#34559D] p-5 text-center text-[6.25vw] font-semibold"
      >
        <p class="pointer-events-none text-white" v-html="check.name"></p>
        <p class="pointer-events-none text-[#EC6261]" v-html="check.time"></p>
        <p class="pointer-events-none text-white" v-html="check.name2"></p>
        <p class="pointer-events-none text-[#EC6261]" v-html="check.time2"></p>
      </a>
    </div>
    <div class="h-5"></div>
    <div>
      <a
        href=""
        class="flex h-[15.625vw] w-[87.5vw] items-center justify-center rounded-xl bg-[#E8C541] text-[6.25vw] font-semibold text-white"
      >
        <p>選課輔導手冊(普通班)</p>
      </a>
    </div>
    <div class="h-7"></div>
  </div>
  <!-- 說明簡報 -->
  <div
    id="briefing"
    class="relative flex w-full flex-col items-center bg-[#EC6261] pt-3"
  >
    <div class="w-[59.375vw]">
      <img src="/assets/Admissions-Briefing.png" alt="" />
    </div>
    <div class="h-8"></div>
    <iframe
      class="h-[51.953vw] w-[78.125vw]"
      src="https://drive.google.com/file/d/1Dgj6tUN1JNS22Dc6OIrYsD9JQH3IYNQM/preview"
      allow="autoplay"
    ></iframe>
    <div class="absolute left-0 bottom-28 w-[28.125vw]">
      <img src="/assets/girl.PNG" alt="" />
    </div>
    <div class="h-20"></div>
    <div class="flex w-full items-center justify-center bg-[#EC6261]">
      <a
        href="@"
        id="line"
        class="w-[67.812vw] rounded-[10px] border-[3px] border-white bg-[#009A35] py-2 text-center text-[5vw] font-semibold text-white"
        ><p class="pointer-events-none">高一家長LINE@群組</p></a
      >
    </div>
    <div class="w-full">
      <img src="/assets/Background2.jpeg" alt="" />
    </div>
  </div>
  <!-- 應辦事項 -->
  <div
    id="matters"
    class="relative flex w-full flex-col items-center bg-[#34559D] py-5"
  >
    <div class="w-[81.25vw]">
      <img src="/assets/Freshmen-should-do.png" class="w-full" alt="" />
    </div>
    <div class="h-8"></div>
    <div class="grid grid-cols-1 gap-y-8">
      <div class="w-[71.875vw]">
        <div class="relative">
          <div
            class="absolute left-[10px] top-[10px] h-[25vw] w-[62.5vw] bg-[#E8C541]"
          ></div>
          <div
            class="absolute flex h-[25vw] w-[62.5vw] items-center justify-center border-2 border-black bg-white text-center text-[6.25vw] font-bold"
          >
            <p>學雜費減免申請<br />(選辦)</p>
          </div>
        </div>
        <div class="h-[30vw]"></div>
        <ul
          class="mt-5 flex list-disc flex-col gap-y-3 pl-7 text-[5vw] font-semibold text-white"
        >
          <a
            :href="matter.href"
            :key="matter.id"
            v-for="matter in datas.matters1"
            ><li v-html="matter.name"></li
          ></a>
        </ul>
      </div>
      <div class="w-[71.875vw]">
        <div class="relative">
          <div
            class="absolute left-[10px] top-[10px] h-[25vw] w-[62.5vw] bg-[#E8C541]"
          ></div>
          <div
            class="absolute flex h-[25vw] w-[62.5vw] items-center justify-center border-2 border-black bg-white text-center text-[6.25vw] font-bold"
          >
            <p>線上訂購校服<br />(超商繳費)</p>
          </div>
        </div>
        <div class="h-[30vw]"></div>
        <ul
          class="mt-5 flex list-disc flex-col gap-y-3 pl-7 text-[5vw] font-semibold text-white"
        >
          <a
            :href="matter.href"
            :key="matter.id"
            v-for="matter in datas.matters2"
            ><li v-html="matter.name"></li
          ></a>
        </ul>
      </div>
      <div class="w-[71.875vw]">
        <div class="relative">
          <div
            class="absolute left-[10px] top-[10px] h-[25vw] w-[62.5vw] bg-[#E8C541]"
          ></div>
          <div
            class="absolute flex h-[25vw] w-[62.5vw] items-center justify-center border-2 border-black bg-white text-center text-[6.25vw] font-bold"
          >
            <p>就學貸款申請<br />(選辦)</p>
          </div>
        </div>
        <div class="h-[30vw]"></div>
        <ul
          class="mt-5 flex list-disc flex-col gap-y-3 pl-7 text-[5vw] font-semibold text-white"
        >
          <a
            :href="matter.href"
            :key="matter.id"
            v-for="matter in datas.matters3"
            ><li v-html="matter.name"></li
          ></a>
        </ul>
      </div>
      <div class="w-[71.875vw]">
        <div class="relative">
          <div
            class="absolute left-[10px] top-[10px] h-[25vw] w-[62.5vw] bg-[#E8C541]"
          ></div>
          <div
            class="absolute flex h-[25vw] w-[62.5vw] items-center justify-center border-2 border-black bg-white text-center text-[6.25vw] font-bold"
          >
            <p>校務系統<br />新生填寫資料</p>
          </div>
        </div>
        <div class="h-[30vw]"></div>
        <ul
          class="mt-5 flex list-disc flex-col gap-y-3 pl-7 text-[5vw] font-semibold text-white"
        >
          <a
            :href="matter.href"
            :key="matter.id"
            v-for="matter in datas.matters4"
            ><li v-html="matter.name"></li
          ></a>
        </ul>
      </div>
      <div class="w-[71.875vw]">
        <div class="relative">
          <div
            class="absolute left-[10px] top-[10px] h-[25vw] w-[62.5vw] bg-[#E8C541]"
          ></div>
          <div
            class="absolute flex h-[25vw] w-[62.5vw] items-center justify-center border-2 border-black bg-white text-center text-[6.25vw] font-bold"
          >
            <p>學生住宿申請<br />(選辦)</p>
          </div>
        </div>
        <div class="h-[30vw]"></div>
        <ul
          class="mt-5 flex list-disc flex-col gap-y-3 pl-7 text-[5vw] font-semibold text-white"
        >
          <a
            :href="matter.href"
            :key="matter.id"
            v-for="matter in datas.matters5"
            ><li v-html="matter.name"></li
          ></a>
        </ul>
      </div>
    </div>
    <div class="w-full place-items-start pt-3">
      <div class="w-[59.375vw]">
        <img src="/assets/boy.PNG" alt="" />
      </div>
    </div>
  </div>
  <!-- 到校日期 -->
  <div
    id="arrive-date"
    class="flex w-full flex-col items-center bg-[#E8C541] py-[10px]"
  >
    <div class="pointer-events-none w-[87.5vw]">
      <img src="/assets/date.png" alt="" class="w-full" />
    </div>
    <div class="h-[24px]"></div>
    <ul class="w-[68.75vw] text-[6.25vw] font-semibold text-white">
      <li>
        <a
          v-for="date in datas.dates"
          :href="date.href"
          :key="date.id"
          class="mb-5 flex h-[31.25vw] items-center justify-center rounded-[10px] bg-[#EC6261] text-center"
          >{{ date.name }}<br />{{ date.name2 }}<br />{{ date.time }}
        </a>
      </li>
    </ul>
  </div>
  <!-- 宣導事項 -->
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

    const datas = reactive({
      lists: [
        {
          href: "#",
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
          href: "#",
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
          href: "#",
          id: "l8",
          name: "新生其他宣導事項",
        },
        {
          href: "#",
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
    });
    return {
      jump,
      datas,
    };
  },
};
</script>
