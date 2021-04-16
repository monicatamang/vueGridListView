<template>
    <section>
        <!-- Adding a click event to the button, when clicked, the function is called and passes a boolean variable as an argument -->
        <button @click="showGridView(isClicked)">Toggle</button>
        <!-- Adding a class binding and using the boolean variable to toggle the class on and off -->
        <article :class="{ gridView: isClicked }">
            <!-- For every tweet in the array, give it a unique id and print the tweet, username and the date created inside of a div tag -->
            <div v-for="tweet in tweets" :key="tweet.userId">
                <h1>
                    {{ tweet.tweet }}
                </h1>
                <p>
                    {{ tweet.username }}
                </p>
                <p>
                    {{ tweet.createdAt }}
                </p>
            </div>
        </article>
    </section>
</template>

<script> 
    // Exporting the body component to the home page
    export default {
        name: "page-body",
        data() {
            return {
                // Declaring a variable to be false as a way to indicate that the toggle button is initially not clicked
                isClicked: false,
                // Declaring an array of 10 tweets as objects
                tweets: [
                    {
                        userId: 1,
                        tweet: "Thanks is short for Tom Hanks",
                        username: "@Co_Mill",
                        createdAt: "03-09-2021",
                    },

                    {
                        userId: 2,
                        tweet: "I hope this email finds you lost at sea",
                        username: "@rudeunicorns",
                        createdAt: "02-21-2021",
                    },

                    {
                        userId: 3,
                        tweet: "People watching is my favourite hobby",
                        username: "@KeithLeakJr",
                        createdAt: "10-28-2019",
                    },

                    {
                        userId: 4,
                        tweet: "Yogurt expires exactly two days before you decide you want it. It's science.",
                        username: "@supershayne",
                        createdAt: "05-01-2020",
                    },

                    {
                        userId: 5,
                        tweet: "I was born at a very young age",
                        username: "@kimmydoesstuff",
                        createdAt: "12-17-2020",
                    },

                    {
                        userId: 6,
                        tweet: "I hope the all pigeons have a great day today",
                        username: `@Will_13`,
                        createdAt: `01-14-2019`,
                    },

                    {
                        userId: 7,
                        tweet: `I just read "22nd" as "secondly second" in my head just now`,
                        username: `@ianhecox`,
                        createdAt: `08-03-2020`,
                    },

                    {
                        userId: 8,
                        tweet: `There isn't a single virgo who believes in astrology`,
                        username: `@sally_t88`,
                        createdAt: `02-08-2017`,
                    },

                    {
                        userId: 9,
                        tweet: `Who called it a subtweet instead of a tea sis statement`,
                        username: `@olivasui`,
                        createdAt: `09-05-2016`,
                    },

                    {
                        userId: 10,
                        tweet: `Why is it called creepypasta and not fettuccino afraido`,
                        username: `@blaine_capatch`,
                        createdAt: `02-03-2021`,
                    }
                ]
            }
        },

        methods: {
            // Creating a function that will flip the value of isClicked when the button is clicked

            // When the button is clicked the first time, the argument that is being passed to the function is false, the isClicked variable from the data function is re-declared as true and a "gridView" class is added to the article which changes the layout of the tweets to a grid view

            // When the button is clicked again, the argument being passed to the function is now true, the isClicked variable from the data function is re-declared as false and the "gridView" class on the article is removed which changes the layout of the tweets to its original layout, a list view
            showGridView: function(toggleOn) {
                this.isClicked = !toggleOn;
            }
        }
    }
</script>

<style scoped>

    section {
        display: grid;
        place-items: center;
        row-gap: 20px;
    }

    article {
        display: grid;
        place-items: center;
        row-gap: 20px;
    }

    .gridView {
        display: grid;
        place-items: center;
        grid-template-columns: 1fr 1fr 1fr;
        column-gap: 20px;
        row-gap: 30px;
    }

    div {
        display: grid;
        place-items: center;
        box-shadow: 1px 1px 5px lightgrey;
        width: 30vw;
        height: 100%;
        padding: 1%;
    }

    button {
        color: white;
        font-size: 1rem;
        font-weight: bold;
        background: skyblue;
        border: none;
        padding: 1%;
        box-shadow: 1px 1px 5px lightgrey;
        margin-bottom: 5vh;
        cursor: pointer;
    }

    button:active {
        box-shadow: none;
    }

    button:focus {
        outline: none;
    }

    h1 {
        color: skyblue;
    }
</style>