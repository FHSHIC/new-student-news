<template>
  <!-- 選單 -->
  <div class="top-0">
    <div
      @click="jump()"
      id="list-button"
      class="fixed flex h-[9.375vw] w-full cursor-pointer items-center justify-center bg-white/20 text-[3.75vw] font-semibold text-white"
    >
      <p class="pointer-events-none">快捷選單</p>
    </div>
    <div
      id="jump"
      class="fixed flex w-[62.5vw] -translate-x-[62.5vw] flex-col items-center bg-[#34559D] p-[18px] duration-200"
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
          href: "#",
          id: "l3",
          name: "入學說明簡報",
        },
        {
          href: "#",
          id: "l4",
          name: "高一家長Line@群組",
        },
        {
          href: "#",
          id: "l5",
          name: "新生暑假作業",
        },
        {
          href: "#",
          id: "l6",
          name: "新生應辦及選辦事項",
        },
        {
          href: "#",
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
    });
    return {
      jump,
      datas,
    };
  },
};
</script>
