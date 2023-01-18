<template>
    <Head title="Address" />

    <AuthenticatedLayout>
        <div class="mt-8"></div>

        <div class="max-w-[500px] mx-auto text-2xl font-extrabold">
            <div>Add a new address</div>

            <form @submit.prevent="submit">
                <div class="text-[15px] -mb-1.5 font-extrabold">Country</div>
                <select
                v-model="form.country"
                    class="w-full border-gray-200 rounded-lg shadow-md py-1 bg-gray-200 hover:bg-gray-200 cursor-pointer focus:border-orange-400 focus:ring-orange-400"
                    name="country"
                >
                    <option selected value="Uzbekistan">Uzbekistan</option>
                    <option value="Kazakhstan">Kazakhstan</option>
                    <option value="Russia">Russia</option>
                    <option value="Armenia">Armenia</option>
                </select>
                <div class="mt-4">
                    <InputLabel class="-mb-1.5" value="First name" />
                    <TextInput v-model="form.first_name" type="text" class="mt-1 block w-full" required />
                </div>
                <div class="mt-3">
                    <InputLabel class="-mb-1.5" value="Last name" />
                    <TextInput  v-model="form.last_name" type="text" class="mt-1 block w-full" required />
                </div>
                <div class="mt-3">
                    <InputLabel class="-mb-1.5" value="Address" />
                    <TextInput
                    v-model="form.addr1"
                        type="text"
                        class="mt-1 block w-full"
                        required
                        placeholder="Address line 1"
                    />
                    <TextInput
                    v-model="form.addr2"
                        type="text"
                        class="mt-1 block w-full"
                        required
                        placeholder="Address line 2"
                    />
                </div>
                <div class="mt-3">
                    <div class="flex gap-2">
                        <div class="w-full">
                            <InputLabel class="-mb-1.5" value="City" />
                            <TextInput
                            v-model="form.city"
                                type="text"
                                class="mt-1 block w-full"
                                required
                                placeholder="City"
                            />
                        </div>
                        <div class="w-full">
                            <InputLabel class="-mb-1.5" value="Postcode" />
                            <TextInput
                            v-model="form.postcode"
                                type="text"
                                class="mt-1 block w-full"
                                required
                                placeholder="Postcode"
                            />
                        </div>  
                    </div>
                </div>
                <div class="mt-6">
                    <button class="bg-yellow-400 p-2 font-bold text-[14px] rounded-lg shadow-sm cursor-pointer">
                        Add address
                    </button>
                </div>
            </form>
        </div>
    </AuthenticatedLayout>
</template>

<script setup>
import AuthenticatedLayout from "@/Layouts/AuthenticatedLayout.vue";
import { Head, Link, useForm, usePage } from "@inertiajs/inertia-vue3";
import { toRefs } from "vue";
import MapMarkerOutlineIcon from "vue-material-design-icons/MapMarkerOutline.vue";
import PlusIcon from "vue-material-design-icons/Plus.vue";
import InputLabel from "@/Components/InputLabel.vue";
import TextInput from "@/Components/TextInput.vue";

const form = useForm({
    country: 'Uzbekistan',
    first_name: usePage().props.value.auth.user.first_name,
    last_name: usePage().props.value.auth.user.last_name,
    addr1: '',
    addr2: '',
    city: '',
    postcode: '',
})

const submit = () => {
    form.post(route('address_options.store'), {
        onFinish: () => route('address.index'),
    })
}

</script>
