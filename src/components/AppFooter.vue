<script>
    export default{
        data(){
            return{
                nav:[
                    {
                        bookings: [
                            '502 New Design Str,', 
                            'Melbourne, San Francisco,', 
                            'CA 94110, United States Of',
                            'America Australia',
                            'T: 1123-456-789',
                            'Email: demo@example.com'
                        ]
                    },
                    {
                        information:[
                            'Product Support',
                            'Checkout',
                            'Report Abuse',
                            'Redeem Voucher',
                            'Order Status'
                        ]
                    },
                    {
                        support: [
                            'Policies & Rules',
                            'Privacy Policy',
                            'License Policy',
                            'My Account',
                            'Locality'
                        ]
                    }
                    
                ]
            }
        }
    }
</script>

<template>
    <section id="nav-footer">
        <div class="container">
            <div class="row">
                <div class="col">
                    <ul>
                        <p class="title">BOOKINGS</p>
                        <li v-for="booking in nav[0].bookings" :key="booking">
                        <a href="#">{{ booking }}</a>
                        </li>
                    </ul>
                </div>
        
                <div class="col">
                    <ul>
                        <p class="title">INFORMATION</p>
                        <li v-for="info in nav[1].information" :key="info">
                        <a href="#">{{ info }}</a>
                        </li>
                    </ul>
                </div>
        
                <div class="col">
                    <ul>
                        <p class="title">SUPPORT</p>
                        <li v-for="sup in nav[2].support" :key="sup">
                        <a href="#">{{ sup }}</a>
                        </li>
                    </ul>
                </div>

                <div class="col">
                    <p class="title">NEWSLETTER</p> 
                    <div class="form">
                        <input type="email" class="email" placeholder="Email">
                        <textarea name="message" id="message" rows="3" placeholder="Message"></textarea>
                        <p class="button">SEND MESSAGE</p>
                    </div>
                </div>
            </div>
      </div>
    </section>

    <section class="footer">
        <div class="hr"></div>
        <p class="text-center">2023 All Rights Reserved. Developed By TemplateMela</p>
        <div class="hr"></div>
    </section>
  </template>

<style lang="scss" scoped>
@use '../styles/partials/mixins.scss' as *;
@use '../styles/partials/variables.scss' as *;

  #nav-footer{
    padding-bottom: 100px;
    .title{
        font-weight: bold;
        font-size: 25px;
        padding: 10px 0;
    }

    a{
        color: rgb(157, 157, 157);
        font-size: 12px;
    }

    a:hover{
        color: $orange-color;
    }

    .form{
        @include flex;
        align-items: start;
        flex-direction: column;
        gap: 10px;

        .email,
        #message{
        background-color: black;
        color: white;
        border: 1px solid rgb(157, 157, 157);
        padding: 8px;
        font-size: 12px;
        width: 100%;
        }

        .button{
            font-size: 12px;
        }
    }
  }

  .footer{

    .hr{
        width: 100%;
        margin: 0;
        border: 0.2px solid rgb(157, 157, 157);
    }

    p{
        padding: 20px;
    }
  }
    


</style>