<script setup>
import { ref } from "vue";
import { Link } from "@inertiajs/inertia-vue3";
import MapMarkerOutlineIcon from "vue-material-design-icons/MapMarkerOutline.vue";
import MenuDownIcon from "vue-material-design-icons/MenuDown.vue";
import MagnifyIcon from "vue-material-design-icons/Magnify.vue";
import MenuIcon from "vue-material-design-icons/Menu.vue";
import CartMinusIcon from "vue-material-design-icons/CartMinus.vue";
import AccountCircleIcon from "vue-material-design-icons/AccountCircle.vue";
import CloseIcon from "vue-material-design-icons/Close.vue";
import ChevronRightIcon from "vue-material-design-icons/ChevronRight.vue";

let showMenu = ref(false);
let accountAndList = ref(false);

const accountAndListFunc = (bool) => {
    setTimeout(() => {
        accountAndList.value = bool;
    }, 150);
};
</script>

<template>
    <div class="min-w-[1150px] bg-gray-100 h-full">
        <div
            v-if="accountAndList"
            class="top-0 z-20 fixed w-full h-full bg-black bg-opacity-50"
        ></div>
        <div
            class="flex items-center bg-gray-900 h-[60px] py-2 fixed z-50 min-w-[1150px] w-full"
        >
            <div class="flex">
                <Link
                    class="text-white h=[50px] p-2 pt-3 border-[1px] border-gray-900 rounded-sm hover:border-[1px] hover:border-gray-100 cursor-pointer"
                >
                    <img width="100" src="/images/logo/AMAZON_LOGO.png" />
                </Link>
            </div>
            <div
                class="text-white h=[50px] p-2 border-[1px] border-gray-900 rounded-sm hover:border-[1px] hover:border-gray-100 cursor-pointer"
            >
                <div class="flex items-center justify-center">
                    <MapMarkerOutlineIcon
                        class="pt-2 -ml-1"
                        fillColor="#f5f5f5"
                    />
                    <div>
                        <div class="text-[12px] text-gray-300 font-extrabold">
                            <div>Delivery to</div>
                        </div>
                        <div
                            class="text-[15px] text-white -mt-1 font-extrabold"
                        >
                            <div>Uzbekistan</div>
                        </div>
                    </div>
                </div>
            </div>
            <div class="flex grow items-center h-[45] px-1">
                <div
                    class="flex items-center justify-center bg-gray-100 border-r border-r-gray-300 font-extrabold text-[11px] text-gray-600 w-[60px] h-[40px] rounded-l-md cursor-pointer hover:bg-gray-200"
                >
                    <div class="pt-[3px]">All</div>
                    <MenuDownIcon
                        fillColor="#5E5E5E"
                        :size="20"
                        class="-mr-2"
                    />
                </div>
                <input
                    class="block w-full border-none border-transparent focus:border-transparent focus:ring-0"
                    type="text"
                />
                <div
                    class="cursor-pointer bg-orange-300 p-[5px] px-2 rounded-r-md hover:bg-orange-400"
                >
                    <MagnifyIcon :size="30" />
                </div>
            </div>
            <div class="flex">
                <div
                    class="h=[50px] p-2 border-[1px] border-gray-900 rounded-sm hover:border-[1px] hover:border-gray-100 cursor-pointer"
                >
                    <div class="flex items-center justify-center mt-2.5 px-1">
                        <img
                            class="mb-3 mr-1"
                            width="23"
                            src="/images/flags/US.png"
                        />
                        <div
                            class="text-[15px] text-white -mt-2 -mr-0.5 font-extrabold"
                        >
                            EN
                        </div>
                        <MenuDownIcon
                            fillColor="#c2c2c2"
                            :size="20"
                            class="-mr-4 -mt-1.5 pr-1"
                        />
                    </div>
                </div>
                <div
                    @mouseenter="accountAndListFunc(true)"
                    @mouseleave="accountAndListFunc(false)"
                    class="h=[50px] p-2 border-[1px] border-gray-900 rounded-sm hover:border-[1px] hover:border-gray-100 cursor-pointer"
                >
                    <div class="flex items-center justify-center">
                        <div>
                            <div class="text-[12px] text-white font-extrabold">
                                Hello,
                                <span>sign in</span>
                            </div>
                            <div class="flex items-center">
                                <div
                                    class="text-[15px] text-white -mt-1.5 font-extrabold"
                                >
                                    Account & List
                                </div>
                                <MenuDownIcon
                                    fillColor="#c2c2c2"
                                    :size="20"
                                    class="-mr-4 -mt-1 pr-1"
                                />
                            </div>
                        </div>
                    </div>
                    <div
                        v-if="accountAndList"
                        class="bg-white absolute z-50 top-[56px] -ml-[230px] w-[480px] rounded-sm px-6"
                    >
                        <div>
                            <div
                                class="flex items-center justify-between py-2.5 border-b"
                            >
                                <div class="text-smp-2">
                                    Who's shopping? Select a profile.
                                </div>
                                <div
                                    class="flex items-center text-sm font-bold text-teal-600 hover:text-red-600 hover:underline"
                                >
                                    Manage Profile
                                    <ChevronRightIcon
                                        :size="20"
                                        fillColor="#808080"
                                    />
                                </div>
                            </div>
                            <div class="flex">
                                <div class="w-1/2 border-r">
                                    <div class="pb-3">
                                        <div class="font-extrabold pt-3">
                                            Your List
                                        </div>
                                        <div
                                            class="text-sm hover:text-red-600 hover:underline pt-3"
                                        >
                                            Create a list
                                        </div>
                                    </div>
                                </div>
                                <div class="w-1/2 ml-5">
                                    <div class="pb-3">
                                        <div class="font-extrabold pt-3">
                                            Your Account
                                        </div>
                                        <div
                                            class="text-sm hover:text-red-600 hover:underline pt-3"
                                        >
                                            Account
                                        </div>
                                        <div
                                            class="text-sm hover:text-red-600 hover:underline pt-3"
                                        >
                                            Sign Out
                                        </div>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
                <div
                    class="h=[50px] p-2 border-[1px] border-gray-900 rounded-sm hover:border-[1px] hover:border-gray-100 cursor-pointer"
                >
                    <div class="flex items-center justify-center">
                        <div>
                            <div class="text-[12px] text-white font-extrabold">
                                Returns
                            </div>
                            <div class="flex items-center">
                                <div
                                    class="text-[15px] text-white -mt-1.5 font-extrabold"
                                >
                                    & Orders
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
                <div
                    class="relative h=[50px] p-2 border-[1px] border-gray-900 rounded-sm hover:border-[1px] hover:border-gray-100 cursor-pointer"
                >
                    <div class="flex items-center justify-center">
                        <span
                            class="absolute text-center right-[21px] w-[14px] -top-0 rounded-full text-[20px]"
                        >
                            <div
                                class="text-orange-400 font-extrabold bg-gray-900 h-[16px]"
                            >
                                0
                            </div>
                        </span>
                        <CartMinusIcon
                            fillColor="#FCFCFC"
                            :size="40"
                            class="-mt-0.5"
                        />
                    </div>
                </div>
            </div>
        </div>

        <div
            class="flex items-center justify-between bg-[#232f3e] h-[38px] fixed z-40 min-w-[1150px] w-full mt-[60px]"
        >
            <div class="flex">
                <div
                    @click="showMenu = true"
                    class="flex h-[30px] border-[1px] border-[#232f3e] rounded-sm hover:border-[1px] hover:border-gray-100 cursor-pointer"
                >
                    <div class="flex items-center justify-between px-2">
                        <MenuIcon
                            fillColor="#F5F5F5"
                            :size="26"
                            class="mr-0.5"
                        />
                        <div class="text-[14px] text-white font-extrabold">
                            All
                        </div>
                    </div>
                </div>
                <div
                    class="flex h-[30px] border-[1px] border-[#232f3e] rounded-sm hover:border-[1px] hover:border-gray-100 cursor-pointer"
                >
                    <div class="flex items-center justify-between px-2">
                        <div class="text-[14px] text-white font-extrabold">
                            Today's Deals
                        </div>
                    </div>
                </div>
                <div
                    class="flex h-[30px] border-[1px] border-[#232f3e] rounded-sm hover:border-[1px] hover:border-gray-100 cursor-pointer"
                >
                    <div class="flex items-center justify-between px-2">
                        <div class="text-[14px] text-white font-extrabold">
                            Customer Service
                        </div>
                    </div>
                </div>
                <div
                    class="flex h-[30px] border-[1px] border-[#232f3e] rounded-sm hover:border-[1px] hover:border-gray-100 cursor-pointer"
                >
                    <div class="flex items-center justify-between px-2">
                        <div class="text-[14px] text-white font-extrabold">
                            Registry
                        </div>
                    </div>
                </div>
                <div
                    class="flex h-[30px] border-[1px] border-[#232f3e] rounded-sm hover:border-[1px] hover:border-gray-100 cursor-pointer"
                >
                    <div class="flex items-center justify-between px-2">
                        <div class="text-[14px] text-white font-extrabold">
                            Gift Cards
                        </div>
                    </div>
                </div>
                <div
                    class="flex h-[30px] border-[1px] border-[#232f3e] rounded-sm hover:border-[1px] hover:border-gray-100 cursor-pointer"
                >
                    <div class="flex items-center justify-between px-2">
                        <div class="text-[14px] text-white font-extrabold">
                            Sell
                        </div>
                    </div>
                </div>
            </div>
            <div class="flex">
                <div
                    class="flex h-[30px] border-[1px] border-[#232f3e] rounded-sm hover:border-[1px] hover:border-gray-100 cursor-pointer"
                >
                    <div class="flex items-center justify-between px-2">
                        <div class="text-[14px] text-white font-extrabold">
                            Holiday Fasion Deals
                        </div>
                    </div>
                </div>
            </div>
        </div>

        <main class="max-w-[1500px] mx-auto">
            <div class="pt-[98px]"></div>
            <slot />
        </main>

        <div class="w-full bg-white mt-10 overflow-x-scroll">
            <div class="max-w[1500px] mx-auto">
                <div class="text-[23px] pt-4 font-extrabold">
                    Recommended based on your shopping trends
                </div>
                <div class="flex justify-center items-stretch">
                    <div v-for="product in $page.props.random_products" :key="product">
                        <div class="p-4 text-center mx-auto">
                            <div class="w-[158px] h-[150px] overflow-hidden">
                                <img
                                    :src="product.image"
                                    
                                />
                            </div>
                            <div
                                class="w-[160px] text-[12px] py-2 text-teal-600 font-extrabold hover:text-red-600 cursor-pointer"
                            >
                                {{product.title.substring(0,40)}}...
                            </div>
                            <div class="flex justify-start">
                                <div
                                    class="text-xs font-extrabold text-red-600 w-full text-left"
                                >
                                    {{ product.price }}
                                </div>
                                <img width="50" src="/images/logo/PRIME_LOGO.png" alt="">
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>

        <footer class="bg-[#232F3E]">
            <div
                class="bg-[#37475A] hover:bg-gray-600 w-full p-3.5 cursor-pointer text-[14px] text-white font-extrabold text-center"
            >
                Back to top
            </div>
            <div
                class="flex items-stretch justify-between max-w-[1000px] mx-auto pt-10 text-white"
            >
                <ul>
                    <li class="font-extrabold text-lg">Get to Know Us</li>
                    <li class="hover:underline cursor-pointer text-[14px]">
                        Careers
                    </li>
                    <li class="hover:underline cursor-pointer text-[14px]">
                        About Amazon
                    </li>
                    <li class="hover:underline cursor-pointer text-[14px]">
                        Investor Relations
                    </li>
                    <li class="hover:underline cursor-pointer text-[14px]">
                        Amazon Devices
                    </li>
                    <li class="hover:underline cursor-pointer text-[14px]">
                        Amazon Science
                    </li>
                </ul>
                <ul>
                    <li class="font-extrabold text-lg">Make Money with Us</li>
                    <li class="hover:underline cursor-pointer text-[14px]">
                        Sell products on Amazon
                    </li>
                    <li class="hover:underline cursor-pointer text-[14px]">
                        Sell on Amazon Business
                    </li>
                    <li class="hover:underline cursor-pointer text-[14px]">
                        Sell apps on Amazon
                    </li>
                    <li class="hover:underline cursor-pointer text-[14px]">
                        Become an Affiliate
                    </li>
                    <li class="hover:underline cursor-pointer text-[14px]">
                        Advertise Your Products
                    </li>
                    <li class="hover:underline cursor-pointer text-[14px]">
                        Self-Publish with Us
                    </li>
                    <li class="hover:underline cursor-pointer text-[14px]">
                        Host an Amazon Hub
                    </li>
                </ul>
                <ul>
                    <li class="font-extrabold text-lg">
                        Amazon Payment Products
                    </li>
                    <li class="hover:underline cursor-pointer text-[14px]">
                        Amazon Business Card
                    </li>
                    <li class="hover:underline cursor-pointer text-[14px]">
                        Shop with Points
                    </li>
                    <li class="hover:underline cursor-pointer text-[14px]">
                        Reload Your Balance
                    </li>
                    <li class="hover:underline cursor-pointer text-[14px]">
                        Amazon Currency Converter
                    </li>
                </ul>
                <ul>
                    <li class="font-extrabold text-lg">Let Us Help You</li>
                    <li class="hover:underline cursor-pointer">
                        Amazon and COVID-19
                    </li>
                    <li class="hover:underline cursor-pointer">Your Account</li>
                    <li class="hover:underline cursor-pointer">Your Orders</li>
                    <li class="hover:underline cursor-pointer">
                        Shipping Rates & Policies
                    </li>
                    <li class="hover:underline cursor-pointer">
                        Returns & Replacements
                    </li>
                    <li class="hover:underline cursor-pointer">
                        Manage Your Content and Devices
                    </li>
                    <li class="hover:underline cursor-pointer">
                        Amazon Assistant
                    </li>
                    <li class="hover:underline cursor-pointer">Help</li>
                </ul>
            </div>
        </footer>
    </div>

    <div
        v-if="showMenu"
        class="top-0 z-50 fixed w-full h-full bg-black bg-opacity-70"
        :class="[
            showMenu ? 'animate__animated animate__fadeIn animate__faster' : '',
        ]"
    >
        <CloseIcon
            @click="showMenu = false"
            :size="30"
            fillColor="#DCDCDC"
            class="ml-2.5 mt-3.5 left-80 cursor-pointer fixed z-50"
            :class="[
                showMenu
                    ? 'animate__animated animate__fadeIn animate__faster'
                    : '',
            ]"
        />
        <div
            class="w-80 h-full bg-white"
            :class="[
                showMenu
                    ? 'animate__animated animate__slideInLeft animate__faster'
                    : '',
            ]"
        >
            <div
                class="bg-[#232f3e] font-extrabold text-[18px] flex items-center p-2 text-white pl-7"
            >
                <span>Hello, Sign in</span>
            </div>

            <div
                class="font-extrabold text-[16px] pt-3 pb-1 pl-6 pr-3 text-black"
            >
                Shop By Department
            </div>
            <div v-for="cat in $page.props.categories" :key="cat">
                <div class="hover:bg-gray-200 pl-6 pr-3">
                    <Link
                        hred="/"
                        class="py-2.5 text-[13px] text-black flex justify-between items-center hover:bg-gray-200 cursor-pointer"
                    >
                        {{ cat.name }}
                        <ChevronRightIcon :size="20" fillColor="#808080" />
                    </Link>
                </div>
            </div>
        </div>
    </div>
</template>
