<script setup>
import AppConfig from '@/layout/AppConfig.vue';
import { ref } from 'vue';
import { useRouter } from 'vue-router';

const router = useRouter();

const val1 = ref(null);
const val2 = ref(null);
const val3 = ref(null);
const val4 = ref(null);

const navigateToDashboard = () => {
    router.push('/');
};

const onDigitInput = (event) => {
    let element;
    if (event.code !== 'Backspace') {
        if (event.code.includes('Numpad') || event.code.includes('Digit')) {
            element = event.target.nextElementSibling;
        }
    }
    if (event.code === 'Backspace') {
        element = event.target.previousElementSibling;
    }

    if (element == null) return;
    else element.focus();
};
</script>
<template>
    <div class="surface-0">
        <div class="flex align-items-center justify-content-between flex-column h-screen">
            <div class="flex flex-column align-items-center justify-content-center w-full md:w-4 h-full text-center py-6 px-4">
                <a @click="navigateToDashboard" class="mb-6" style="cursor: pointer">
                    <svg height="56" viewBox="0 0 17 20" fill="none" xmlns="http://www.w3.org/2000/svg">
                        <path d="M0 0H6.00019V3.82345L17 1.66667V6.66667L6.00019 8.82345V10.4901L17 8.33333V13.3333L6.00019 15.4901V20H0V0Z" fill="url(#paint0_linear)" />
                        <defs>
                            <linearGradient id="paint0_linear" x1="3.33335" y1="3.08442e-08" x2="8.49995" y2="20" gradientUnits="userSpaceOnUse">
                                <stop stop-color="var(--primary-400)" />
                                <stop offset="1" stop-color="var(--primary-700)" />
                            </linearGradient>
                        </defs>
                    </svg>
                </a>
                <div class="mb-4">
                    <div class="text-900 text-xl font-bold mb-2">Verification</div>
                    <span class="text-600 font-medium">We have sent code to you email:</span>
                    <div class="flex align-items-center mt-1">
                        <i class="pi pi-envelope text-600"></i>
                        <span class="text-900 font-bold ml-2">dm**@gmail.com</span>
                    </div>
                </div>
                <div class="flex flex-column">
                    <div class="flex justify-content-between w-full align-items-center mb-4 gap-3">
                        <InputText v-model="val1" class="w-3rem text-center text-color-secondary surface-50 border-200" maxlength="1" @keyup="onDigitInput($event)" />
                        <InputText v-model="val2" class="w-3rem text-center text-color-secondary surface-50 border-200" maxlength="1" @keyup="onDigitInput($event)" />
                        <InputText v-model="val3" class="w-3rem text-center text-color-secondary surface-50 border-200" maxlength="1" @keyup="onDigitInput($event)" />
                        <InputText v-model="val4" class="w-3rem text-center text-color-secondary surface-50 border-200" maxlength="1" @keyup="onDigitInput($event)" />
                    </div>

                    <div class="flex flex-wrap gap-2 justify-content-between">
                        <Button label="Cancel" class="flex-auto" outlined @click="navigateToDashboard"></Button>
                        <Button label="Verify" class="flex-auto" @click="navigateToDashboard"></Button>
                    </div>
                </div>
            </div>
            <div class="flex flex-wrap align-items-center pb-8 px-4">
                <h4 class="m-0 mr-5" style="line-height: 22px">freya</h4>
                <h6 class="m-0 font-medium text-300" style="line-height: 17px">Copyright Ⓒ PrimeTek Informatics</h6>
            </div>
        </div>
    </div>

    <AppConfig simple />
</template>
