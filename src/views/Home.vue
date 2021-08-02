<template>
    <h1 class="font-bold text-center text-3xl pb-5" v-if="isEnabled">V Show</h1>
    <ul class="list-inside text-center mx-auto">
        <li v-for="fruit, index in fruits" :key="index">{{ index }} -{{ fruit }}</li>
    </ul>

    <div class="max-w-md mx-auto bg-gray-300 p-5" v-for="actor in actors" :key="actor.name">
        <h2>{{actor.name}}</h2>
        <h4 v-for="movie in actor.movies" :key="movie"> {{ movie }}</h4>
    </div>

    <h2 class="text-center"> add - {{ add(5,5,5)}} </h2>

    <div class="max-w-md mx-auto container text-enter">
      <h1 class="mb-10"><pre>{{JSON.stringify(formData, null, 2)}}</pre></h1>
      <form action="">
        <input class="w-full mb-4" type="text" id="fname" v-model="formData.fname">
        <textarea class="w-full" id="profileSummary" v-model="formData.profileSummary"></textarea>
      </form>
    </div>
</template>


<script>
    export default {
        name: "Learn",
        data() {
            return {
                question: "Ready to dive in?",
                answer: "SpaceWorks Starter App",
                isEnabled: false,
                fruits: ['apple', 'banana', 'orange', 'mango', 'pineapple'],
                actors: [{
                        name: "Christian Bale",
                        movies: ['a', 'b', 'c']
                    },
                    {
                        name: "D Caprio",
                        movies: ['x', 'y', 'z']
                    },
                ],
                formData: {
                  fname: "",
                  profileSummary: ""
                }
            }
        },
        methods: {
            add(a, b, c) {
                return a + b + c;
            },
        }
    }
</script>