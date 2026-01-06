<script setup lang="ts">
import { ref } from 'vue'

const authDialog = ref(null)

const currentForm = ref('login')

function openAuthForm() {
  authDialog.value.showModal()
}
function closeDialog() {
  authDialog.value.close()
}

function switchForm(mode) {
  currentForm.value = mode
}

defineExpose({
  openAuthForm,
})
</script>

<template>
  <!-- Open the modal using ID.showModal() method -->
  <!-- <button class="btn" onclick="my_modal_5.showModal()">open modal</button> -->
  <dialog ref="authDialog" class="modal modal-bottom sm:modal-middle !h-[900px] p-5">
    <div class="modal-box relative flex flex-col justify-center items-center">
      <div>
        <button class="btn btn-active absolute right-5 top-3 bg-transparent w-[30px] h-[30px] p-0 flex items-center " @click="closeDialog">
          <img src="@/image/icon-close.png" alt="" />

        </button>
      </div>

      <div class="flex gap-5 mt-5">
        <button
          @click="switchForm('login')"
          class="btn btn-active bg-[#E6B566] text-[#4A1F00] w-[150px] h-[36px]"
        >
          登入
        </button>
        <button
          @click="switchForm('register')"
          class="btn btn-active bg-transparent border w-[150px] h-[36px] border-[#E6B566] text-[#E6B566]"
        >
          註冊
        </button>
      </div>
      <div class="mt-4" v-if="currentForm === 'login'">
        <fieldset class="fieldset bg-base-200 border-base-300 rounded-box w-xs border p-6">
          <!-- <legend class="fieldset-legend">Login</legend> -->

          <label class="label text-sm">帳號/Email</label>
          <input type="email" class="input" placeholder="Email" />

          <label class="label text-sm">密碼</label>
          <input type="password" class="input" placeholder="Password" />
          <div class="flex justify-center mt-3">
            <button class="btn btn-active bg-[#E6B566] text-[#4A1F00] w-full h-[36px]">登入</button>
          </div>
        </fieldset>
      </div>

      <!-- 註冊表單 -->
      <div class="mt-4" v-if="currentForm === 'register'">
        <fieldset class="fieldset bg-base-200 border-base-300 rounded-box w-xs border p-6">
          <!-- <legend class="fieldset-legend">Login</legend> -->
          <div class="flex flex-col gap-5">
            <div>
              <label class="label text-sm">暱稱/名字</label>
              <input type="email" class="input" placeholder="Email" />
            </div>
            <div>
              <label class="label text-sm">出生日期</label>
              <input type="date" class="input" />
            </div>

            <div>
              <label class="label text-sm">帳號/Email</label>
              <input type="email" class="input" placeholder="Email" />
            </div>

            <div>
              <label class="label text-sm">密碼</label>
              <input type="password" class="input" placeholder="Password" />
            </div>
            <fieldset class="fieldset border-base-300 rounded-box w-64 border p-4 mt-3">
              <!-- <legend class="fieldset-legend">Login options</legend> -->
              <label class="label">
                <input type="checkbox" class="checkbox" />
                我已閱讀並同意註冊條款，並遵守網站使用規範
              </label>
            </fieldset>
          </div>
          <div class="flex justify-center mt-3">
            <button class="btn btn-active bg-[#E6B566] text-[#4A1F00] w-full h-[36px]">登入</button>
          </div>
        </fieldset>
      </div>
    </div>
  </dialog>
</template>
