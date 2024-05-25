<template>
    <Header :currentIndex="activeBlocks" />
    <transition name="slide-fade" mode="out-in">
        <div :key="currentIndex" id="containerT" class="container1 duration-200">
            <div v-if="activeBlocks.includes(0)"
                class="mt-[250px] flex my-10 relative z-1 flex col justify-center items-center">
                <div class="flex flex-col max-w-[600px]">
                    <div class="text-2xl mb-2">How much will you take in card payments in the next 12 months?</div>
                    <div class="text-[16px] mb-5">This will help us estimate your annual card turnover</div>
                    <div class="relative mb-5">
                        <span
                            class="bg-[#f7d147] w-6 h-6 rounded-full outline-none absolute left-6 top-[calc(50%_-_12px)] flex items-center justify-center">£</span>
                        <input placeholder="50,000"
                            class="py-6 border border-solid border-[#a49d7d33] text-xl pl-20 pr-4 w-full" />
                    </div>
                    <div class="bg-[#f8f4e6] p-4 flex flex-col">
                        <div class="flex items-center mb-4"><svg xmlns="http://www.w3.org/2000/svg" width="24px"
                                height="24px" viewBox="0 0 24 24" fill="none">
                                <path
                                    d="M12 0L14.6942 8.2918H23.4127L16.3593 13.4164L19.0534 21.7082L12 16.5836L4.94658 21.7082L7.64074 13.4164L0.587322 8.2918H9.30583L12 0Z"
                                    fill="#F7D147"></path>
                            </svg><svg xmlns="http://www.w3.org/2000/svg" width="24px" height="24px" viewBox="0 0 24 24"
                                fill="none">
                                <path
                                    d="M12 0L14.6942 8.2918H23.4127L16.3593 13.4164L19.0534 21.7082L12 16.5836L4.94658 21.7082L7.64074 13.4164L0.587322 8.2918H9.30583L12 0Z"
                                    fill="#F7D147"></path>
                            </svg><svg xmlns="http://www.w3.org/2000/svg" width="24px" height="24px" viewBox="0 0 24 24"
                                fill="none">
                                <path
                                    d="M12 0L14.6942 8.2918H23.4127L16.3593 13.4164L19.0534 21.7082L12 16.5836L4.94658 21.7082L7.64074 13.4164L0.587322 8.2918H9.30583L12 0Z"
                                    fill="#F7D147"></path>
                            </svg><svg xmlns="http://www.w3.org/2000/svg" width="24px" height="24px" viewBox="0 0 24 24"
                                fill="none">
                                <path
                                    d="M12 0L14.6942 8.2918H23.4127L16.3593 13.4164L19.0534 21.7082L12 16.5836L4.94658 21.7082L7.64074 13.4164L0.587322 8.2918H9.30583L12 0Z"
                                    fill="#F7D147"></path>
                            </svg><svg xmlns="http://www.w3.org/2000/svg" width="24px" height="24px" viewBox="0 0 24 24"
                                fill="none">
                                <path
                                    d="M12 0L14.6942 8.2918H23.4127L16.3593 13.4164L19.0534 21.7082L12 16.5836L4.94658 21.7082L7.64074 13.4164L0.587322 8.2918H9.30583L12 0Z"
                                    fill="#F7D147"></path>
                            </svg></div>
                        <div class="text-[20px] recolleta">"Very good advice freely given that helped me make the
                            decision that
                            was best for me"</div>
                        <div class="flex items-center justify-between">
                            <div class="text-sm flex flex-col">
                                <div class="text-black/50">Trustpilot</div>
                                <div class="font-light">Ruth Tesdale</div>
                            </div>
                            <img src="https://quotes.tuza.co.uk/assets/trustpilot-f26bd861.svg" />
                        </div>
                    </div>
                    <button @click="firstBlock"
                        class="w-[65px] h-[34px] bg-[#f7d147] flex items-center justify-center ml-auto mt-2 rounded-sm font-medium">Next</button>
                </div>
            </div>

            <div v-if="activeBlocks.includes(1)" class="flex fadeIn my-10 flex col justify-center h-full items-center">
                <div class="flex flex-col max-w-[600px] w-[600px]">
                    <div class="text-2xl mb-2">Do you already accept card payments?</div>
                    <div class="text-[16px] mb-5">Let us know if you're already with a card payment provider</div>
                    <div class="flex items-center">
                        <input type="radio" id="test1" name="radio-group">
                        <label @click="secondBlock" for="test1">Yes</label>
                        <input type="radio" id="test2" name="radio-group">
                        <label @click="secondBlock" for="test2">No</label>
                    </div>
                </div>
            </div>

            <div v-if="activeBlocks.includes(2)" class="flex fadeIn flex col my-10 justify-center h-full items-center">
                <div class="flex flex-col max-w-[600px] w-[600px]">
                    <div class="text-2xl mb-2">Want to save time? Upload your merchant statement
                    </div>
                    <div class="text-[16px] mb-5">By uploading your merchant statement, you agree to have read and
                        understood
                        our <a href="" class="text-black border-b border-solid border-black">terms and conditions</a>
                        and <a href="" class="text-black border-b border-solid border-black">privacy policy</a> </div>
                    <div class="flex flex-col p-10 items-center rounded-md border-2 border-dashed border-[#f7d147]">
                        <div class="text-black text-md mb-2">Click to upload or drag and drop</div>
                        <div class="text-black text-[12px]">Click to upload or drag and drop</div>
                    </div>
                    <button @click="thirdBlock"
                        class="w-[65px] h-[34px] bg-[#f7d147] flex items-center justify-center ml-auto mt-2 rounded-sm font-medium">Skip</button>

                </div>
            </div>

            <div v-if="activeBlocks.includes(3)" class="flex fadeIn flex col my-10 justify-center h-full items-center">
                <div class="flex flex-col max-w-[600px] w-[600px]">
                    <div class="text-2xl mb-2">Who is your card payment provider?</div>
                    <div class="text-[16px] mb-5">This will help us to find the best rates for you</div>
                    <div class="grid grid-cols-3 gap-3">
                        <div class="w-[190px] h-[74px] flex items-center justify-center p-6 border-[a49d7d33] border-solid border rounded-md hover:cursor-pointer"
                            :class="{ 'active': this.activeProvider == 1 }"
                            @click="this.activeProvider = 1; fourBlock()">
                            <img src="https://quotes.tuza.co.uk/assets/barclaycardColor-1ab6c98d.png" alt="">
                        </div>
                        <div class="w-[190px] h-[74px] flex items-center justify-center p-6 border-[a49d7d33] border-solid border rounded-md hover:cursor-pointer"
                            :class="{ 'active': this.activeProvider == 2 }"
                            @click="this.activeProvider = 2; fourBlock()">
                            <img src="https://quotes.tuza.co.uk/assets/worldpayColor-67166bdd.png" alt="">
                        </div>
                        <div class="w-[190px] h-[74px] flex items-center justify-center p-6 border-[a49d7d33] border-solid border rounded-md hover:cursor-pointer"
                            :class="{ 'active': this.activeProvider == 3 }"
                            @click="this.activeProvider = 3; fourBlock()">
                            <img src="https://quotes.tuza.co.uk/assets/revolutColor-0c000945.png" alt="">
                        </div>
                        <div class="w-[190px] h-[74px] flex items-center justify-center p-6 border-[a49d7d33] border-solid border rounded-md hover:cursor-pointer"
                            :class="{ 'active': this.activeProvider == 4 }"
                            @click="this.activeProvider = 4; fourBlock()">
                            <img src="data:image/png;base64,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"
                                alt="">
                        </div>
                        <div class="w-[190px] h-[74px] flex items-center justify-center p-6 border-[a49d7d33] border-solid border rounded-md hover:cursor-pointer"
                            :class="{ 'active': this.activeProvider == 5 }"
                            @click="this.activeProvider = 5; fourBlock()">
                            <img src="data:image/png;base64,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"
                                alt="">
                        </div>
                        <div class="w-[190px] h-[74px] flex items-center justify-center p-6 border-[a49d7d33] border-solid border rounded-md hover:cursor-pointer"
                            :class="{ 'active': this.activeProvider == 6 }"
                            @click="this.activeProvider = 6; fourBlock()">
                            <img src="data:image/png;base64,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"
                                alt="">
                        </div>
                        <div class="w-[190px] h-[74px] flex items-center justify-center p-6 border-[a49d7d33] border-solid border rounded-md hover:cursor-pointer"
                            :class="{ 'active': this.activeProvider == 7 }"
                            @click="this.activeProvider = 7; fourBlock()">
                            <img src="https://quotes.tuza.co.uk/assets/evoColor-d4a2d19c.png" alt="">
                        </div>
                        <div class="w-[190px] h-[74px] flex items-center justify-center p-6 border-[a49d7d33] border-solid border rounded-md hover:cursor-pointer"
                            :class="{ 'active': this.activeProvider == 8 }"
                            @click="this.activeProvider = 8; fourBlock()">
                            <img src="https://quotes.tuza.co.uk/assets/squareColor-31bf8602.png" alt="">
                        </div>
                        <div class="w-[190px] h-[74px] flex items-center justify-center p-6 border-[a49d7d33] border-solid border rounded-md hover:cursor-pointer"
                            :class="{ 'active': this.activeProvider == 9 }"
                            @click="this.activeProvider = 9; fourBlock()">
                            <img src="https://quotes.tuza.co.uk/assets/zettleColor-d280bced.png" alt="">
                        </div>

                        <div class="text-md col-span-3 hover:cursor-pointer text-center mt-3 border-b border-solid border-black w-fit mx-auto"
                            @click="showFullList = true" v-if="!showFullList">Show All</div>

                        <div class="w-[190px] h-[74px] flex items-center justify-center p-6 border-[a49d7d33] border-solid border rounded-md hover:cursor-pointer"
                            v-if="showFullList" :class="{ 'active': this.activeProvider == 10 }"
                            @click="this.activeProvider = 10; fourBlock()">
                            <img src="https://quotes.tuza.co.uk/assets/barclaycardColor-1ab6c98d.png" alt="">
                        </div>
                        <div class="w-[190px] h-[74px] flex items-center justify-center p-6 border-[a49d7d33] border-solid border rounded-md hover:cursor-pointer"
                            v-if="showFullList" :class="{ 'active': this.activeProvider == 11 }"
                            @click="this.activeProvider = 11; fourBlock()">
                            <img src="https://quotes.tuza.co.uk/assets/worldpayColor-67166bdd.png" alt="">
                        </div>
                        <div class="w-[190px] h-[74px] flex items-center justify-center p-6 border-[a49d7d33] border-solid border rounded-md hover:cursor-pointer"
                            v-if="showFullList" :class="{ 'active': this.activeProvider == 12 }"
                            @click="this.activeProvider = 12; this.fourBlock()">
                            <img src="https://quotes.tuza.co.uk/assets/revolutColor-0c000945.png" alt="">
                        </div>

                        <div class="w-full col-span-3 h-[74px] flex items-center justify-center p-6 border-[a49d7d33] border-solid border rounded-md hover:cursor-pointer"
                            v-if="showFullList" :class="{ 'active': this.activeProvider == 13 }"
                            @click="this.activeProvider = 13; this.fourBlock()">
                            None of these
                        </div>
                    </div>

                </div>
            </div>

            <div v-if="activeBlocks.includes(4)"
                class="flex fadeIn relative my-10 z-1 flex col justify-center h-full items-center">
                <div class="flex flex-col max-w-[600px] w-[600px]">
                    <div class="text-2xl mb-2">What is your average transaction amount?</div>
                    <div class="text-[16px] mb-5">This is the average amount that customers spend on each purchase</div>
                    <div class="relative mb-5">
                        <span
                            class="bg-[#f7d147] w-6 h-6 rounded-full outline-none absolute left-6 top-[calc(50%_-_12px)] flex items-center justify-center">£</span>
                        <input placeholder="15"
                            class="py-6 border focus:border-black outline-none border-solid border-[#a49d7d33] text-xl pl-20 pr-4 w-full" />
                    </div>

                    <button @click="fiveBlock"
                        class="w-[65px] h-[34px] bg-[#f7d147] flex items-center justify-center ml-auto mt-2 rounded-sm font-medium">Next</button>
                </div>
            </div>

            <div v-if="activeBlocks.includes(5)" class="flex fadeInf lex col my-10 justify-center h-full items-center">
                <div class="flex flex-col max-w-[600px] w-[600px]">
                    <div class="text-2xl mb-2">Is your business registered?</div>
                    <div class="text-[16px] mb-5">This means your business has been registered with Companies House
                    </div>
                    <div class="flex items-center">
                        <input type="radio" id="test3" name="radio-group">
                        <label @click="sixBlock" for="test1">Yes</label>
                        <input type="radio" id="test4" name="radio-group">
                        <label @click="sixBlock" for="test2">No</label>
                    </div>
                </div>
            </div>

            <div v-if="activeBlocks.includes(6)"
                class="flex fadeIn relative my-10 z-1 flex col justify-center h-full items-center">
                <div class="flex flex-col max-w-[600px] w-[600px]">
                    <div class="text-2xl mb-2">What is the name of your business?</div>
                    <div class="text-[16px] mb-5">This is the trading name your customers know you by</div>
                    <div class="relative mb-5 w-full w-[600px]">
                        <input placeholder="Nico's Italian"
                            class="py-6 flex border focus:border-black outline-none border-solid border-[#a49d7d33] text-xl pl-5 pr-4 w-full" />
                    </div>

                    <button @click="sevenBlock"
                        class="w-[65px] h-[34px] bg-[#f7d147] flex items-center justify-center ml-auto mt-2 rounded-sm font-medium">Next</button>
                </div>
            </div>

            <div v-if="activeBlocks.includes(7)"
                class="flex fadeIn relative my-10 z-1 flex col justify-center h-full items-center">
                <div class="flex flex-col max-w-[600px] w-[600px]">
                    <div class="text-2xl mb-2">What does your business do?</div>
                    <div class="text-[16px] mb-5">Tell us a bit about your business and what it does</div>
                    <div class="relative mb-5 w-full w-[600px]">
                        <input placeholder="I sell sandwiches"
                            class="py-6 flex border focus:border-black outline-none border-solid border-[#a49d7d33] text-xl pl-5 pr-4 w-full" />
                    </div>

                    <button @click="eightBlock"
                        class="w-[65px] h-[34px] bg-[#f7d147] flex items-center justify-center ml-auto mt-2 rounded-sm font-medium">Next</button>
                </div>
            </div>

            <div v-if="activeBlocks.includes(8)"
                class="flex fadeIn relative my-10 z-1 flex col justify-center h-full items-center">
                <div class="flex flex-col max-w-[600px] w-[600px]">
                    <div class="text-2xl mb-2">Enter your business trading postcode</div>
                    <div class="flex items-center justify-between">
                        <div class="text-[16px] mb-5">Let us know where you operate your business from</div>
                        <div class="relative">
                            <span @mouseover="showToolTip = true" @mouseleave="showToolTip = false"
                                class="border border-solid border-black rounded-full flex items-center hover:cursor-pointer justify-center w-5 h-5">?</span>
                            <div v-show="showToolTip"
                                class="p-3 text-[12px] bg-[#fff8dd] -bottom-[100px] left-[calc(50%_-_100px)] absolute w-[200px] z-[8] rounded-sm">
                                If you do not have a fixed trading address, please enter your registered business or
                                home
                                address instead.</div>
                        </div>
                    </div>
                    <div class="relative mb-5 w-full w-[600px]">
                        <input placeholder="E8 3RL"
                            class="py-6 flex border focus:border-black outline-none border-solid border-[#a49d7d33] text-xl pl-5 pr-4 w-full" />
                    </div>
                    <div class="text-sm border-b border-solid border-black w-fit hover:cursor-pointer">Enter address
                        manually
                    </div>
                    <button @click="nineBlock"
                        class="w-[65px] h-[34px] bg-[#f7d147] flex items-center justify-center ml-auto mt-2 rounded-sm font-medium">Next</button>
                </div>
            </div>


            <div v-if="activeBlocks.includes(9)"
                class="flex fadeInrelative my-10 z-1 flex col justify-center h-full items-center">
                <div class="flex flex-col max-w-[600px] w-[600px]">
                    <div class="text-2xl mb-2">What is your email address?</div>
                    <div class="flex items-center justify-between">
                        <div class="text-[16px] mb-5">Please enter the email address you’d like us to send your quotes
                            to</div>
                        <div class="relative">
                            <span @mouseover="showToolTip = true" @mouseleave="showToolTip = false"
                                class="border border-solid border-black rounded-full flex items-center hover:cursor-pointer justify-center w-5 h-5">?</span>
                            <div v-show="showToolTip"
                                class="p-3 text-[12px] bg-[#fff8dd] -bottom-[80px] left-[calc(50%_-_100px)] absolute w-[200px] z-[8] rounded-sm">
                                This is where we'll send your quotes to</div>
                        </div>
                    </div>
                    <div class="relative mb-5">
                        <input placeholder="email@domain.com" type="email"
                            class="py-6 border border-solid border-[#a49d7d33] text-xl pl-5 pr-4 w-full" />
                    </div>
                    <div class="bg-[#f8f4e6] p-4 flex flex-col">
                        <div class="flex items-center mb-4"><svg xmlns="http://www.w3.org/2000/svg" width="24px"
                                height="24px" viewBox="0 0 24 24" fill="none">
                                <path
                                    d="M12 0L14.6942 8.2918H23.4127L16.3593 13.4164L19.0534 21.7082L12 16.5836L4.94658 21.7082L7.64074 13.4164L0.587322 8.2918H9.30583L12 0Z"
                                    fill="#F7D147"></path>
                            </svg><svg xmlns="http://www.w3.org/2000/svg" width="24px" height="24px" viewBox="0 0 24 24"
                                fill="none">
                                <path
                                    d="M12 0L14.6942 8.2918H23.4127L16.3593 13.4164L19.0534 21.7082L12 16.5836L4.94658 21.7082L7.64074 13.4164L0.587322 8.2918H9.30583L12 0Z"
                                    fill="#F7D147"></path>
                            </svg><svg xmlns="http://www.w3.org/2000/svg" width="24px" height="24px" viewBox="0 0 24 24"
                                fill="none">
                                <path
                                    d="M12 0L14.6942 8.2918H23.4127L16.3593 13.4164L19.0534 21.7082L12 16.5836L4.94658 21.7082L7.64074 13.4164L0.587322 8.2918H9.30583L12 0Z"
                                    fill="#F7D147"></path>
                            </svg><svg xmlns="http://www.w3.org/2000/svg" width="24px" height="24px" viewBox="0 0 24 24"
                                fill="none">
                                <path
                                    d="M12 0L14.6942 8.2918H23.4127L16.3593 13.4164L19.0534 21.7082L12 16.5836L4.94658 21.7082L7.64074 13.4164L0.587322 8.2918H9.30583L12 0Z"
                                    fill="#F7D147"></path>
                            </svg><svg xmlns="http://www.w3.org/2000/svg" width="24px" height="24px" viewBox="0 0 24 24"
                                fill="none">
                                <path
                                    d="M12 0L14.6942 8.2918H23.4127L16.3593 13.4164L19.0534 21.7082L12 16.5836L4.94658 21.7082L7.64074 13.4164L0.587322 8.2918H9.30583L12 0Z"
                                    fill="#F7D147"></path>
                            </svg></div>
                        <div class="text-[20px] recolleta">"Really efficient transfer of card processing and attention
                            to
                            detail. Highly recommend. Raphael was <a href="" class="text-[#f7d147]">read more</a></div>
                        <div class="flex items-center justify-between">
                            <div class="text-sm flex flex-col">
                                <div class="text-black/50">Trustpilot</div>
                                <div class="font-light">Ruth Tesdale</div>
                            </div>
                            <img src="https://quotes.tuza.co.uk/assets/trustpilot-f26bd861.svg" />
                        </div>
                    </div>
                    <button @click="tenBlock"
                        class="w-[65px] h-[34px] bg-[#f7d147] flex items-center justify-center ml-auto mt-2 rounded-sm font-medium">Next</button>
                </div>
            </div>

            <div v-if="activeBlocks.includes(10)"
                class="flex fadeIn relative my-10 z-1 flex col justify-center h-full items-center">
                <div class="flex flex-col w-[600px] max-w-[600px]">
                    <div class="text-2xl mb-2">What is your name?</div>
                    <div class="text-[16px] mb-5">Please enter your first and last name</div>
                    <div class="w-full flex items-center">
                        <input placeholder="Nico"
                            class="py-6 border border-solid border-[#a49d7d33] text-xl pl-5 pr-4 w-1/2 mr-3" />
                        <input placeholder="Bianchi"
                            class="py-6 border border-solid border-[#a49d7d33] text-xl pl-5 pr-4 w-1/2" />
                    </div>
                    <button @click="elevenBlock"
                        class="w-[65px] h-[34px] bg-[#f7d147] flex items-center justify-center ml-auto mt-2 rounded-sm font-medium">Next</button>
                </div>
            </div>

            <div v-if="activeBlocks.includes(11)"
                class="flex fadeIn relative my-10 z-1 flex col justify-center h-full items-center">
                <div class="flex flex-col max-w-[600px] w-[600px]">
                    <div class="text-2xl mb-2">What is your phone number?</div>
                    <div class="flex items-center justify-between">
                        <div class="text-[16px] mb-5">Please enter your phone number</div>
                        <div class="relative">
                            <span @mouseover="showToolTip = true" @mouseleave="showToolTip = false"
                                class="border border-solid border-black rounded-full flex items-center hover:cursor-pointer justify-center w-5 h-5">?</span>
                            <div v-show="showToolTip"
                                class="p-3 text-[12px] bg-[#fff8dd] -bottom-[150px] left-[calc(50%_-_100px)] absolute w-[200px] z-[8] rounded-sm">
                                To put together the best price and package, we may need to give you a quick call. Don't
                                worry - your quotes are without obligation and our friendly team won't call again if you
                                ask us not to.</div>
                        </div>
                    </div>
                    <div class="relative mb-5 w-full w-[600px]">
                        <input placeholder="+44 7893 932118"
                            class="py-6 flex border focus:border-black outline-none border-solid border-[#a49d7d33] text-xl pl-5 pr-4 w-full" />
                    </div>

                    <button @click="twelveBlock"
                        class="w-[65px] h-[34px] bg-[#f7d147] flex items-center justify-center ml-auto mt-2 rounded-sm font-medium">Next</button>
                </div>
            </div>

            <div v-if="activeBlocks.includes(12)"
                class="flex fadeIn relative my-10 z-1 flex col justify-center h-full items-center">
                <div class="flex flex-col w-[600px] max-w-[600px]">
                    <div class="flex justify-center items-center mb-4">
                        <svg height="160" viewBox="0 0 1270 682" fill="none" xmlns="http://www.w3.org/2000/svg"
                            style="transition: height 250ms ease-in-out 0s;">
                            <path
                                d="M60.31 220C57.7 220 56.134 218.782 56.134 216.694V215.998C56.134 211.126 63.094 209.038 63.094 201.034V115.426C63.094 107.422 56.134 105.334 56.134 100.462V99.766C56.134 97.678 57.7 96.46 60.31 96.46H98.59C101.026 96.46 102.766 97.678 102.766 99.766V100.462C102.766 105.334 94.936 107.422 94.936 115.426V196.51C94.936 202.252 97.372 207.82 103.462 207.82H121.384C136.174 207.82 138.784 183.112 147.136 183.112H149.572C152.182 183.112 153.574 184.852 153.052 187.462L148.528 214.432C147.832 218.26 146.266 220 142.438 220H60.31ZM202.376 221.74C176.45 221.74 158.18 203.992 158.18 177.718C158.18 151.792 178.19 134.914 201.332 134.74C222.038 134.566 235.958 144.658 235.958 159.97C235.958 172.15 224.474 182.242 208.118 184.852C202.028 185.896 195.938 186.244 190.892 186.07C195.416 194.77 202.898 200.164 212.642 200.164C221.342 200.164 228.128 196.684 231.26 192.508C233.696 190.072 237.872 191.116 237.698 194.944C237.35 204.514 227.258 221.74 202.376 221.74ZM185.846 163.45C185.846 168.148 186.368 172.672 187.412 176.848C190.718 177.022 194.024 176.848 196.112 176.5C203.768 175.108 207.944 169.714 207.944 157.708C207.944 150.052 203.594 143.962 197.852 143.962C190.718 143.962 185.846 151.966 185.846 163.45ZM282.063 221.74C265.011 221.74 253.701 210.604 253.701 189.55V148.312H247.263C245.001 148.312 243.261 146.572 243.261 144.31V140.482C243.261 138.046 244.827 136.48 247.263 136.48H250.569C261.183 136.48 269.361 129.52 271.623 118.906C272.319 116.122 274.233 114.382 276.321 114.382H280.497C283.281 114.382 285.021 116.122 285.021 118.906V136.48H303.117C305.205 136.48 307.119 138.22 307.119 140.482V144.31C307.119 146.572 305.205 148.312 303.117 148.312H285.021V190.072C285.021 195.988 288.501 199.468 293.025 199.468C299.637 199.468 302.595 196.162 304.335 193.03C306.771 189.898 310.947 190.942 310.947 194.248C310.947 207.646 301.203 221.74 282.063 221.74ZM324.45 145.354C320.448 147.616 315.75 142.57 318.882 139.438C325.32 132.826 328.452 129.52 328.974 124.474C329.148 122.212 328.8 120.646 326.712 120.646C319.926 120.646 314.184 114.034 314.184 104.464C314.184 93.502 320.97 85.846 331.758 85.846C341.328 85.846 350.202 93.502 350.202 106.9C350.202 121.69 342.024 134.566 324.45 145.354ZM386.61 221.566C364.686 221.566 348.33 213.388 348.33 201.208C348.33 193.378 353.724 190.072 360.684 190.072C378.258 190.072 372.168 213.91 386.61 213.91C391.83 213.91 396.006 211.3 396.006 204.34C396.006 181.546 349.896 194.944 349.896 161.188C349.896 145.702 364.86 134.74 386.61 134.74C408.708 134.74 423.324 144.31 423.324 155.62C423.324 161.71 418.104 166.234 411.492 166.234C394.788 166.234 400.182 142.744 388.176 142.744C382.782 142.744 380.172 147.616 380.172 152.662C380.172 176.5 424.716 163.972 424.716 195.988C424.716 210.43 410.796 221.566 386.61 221.566ZM648.111 220C645.675 220 644.109 218.782 644.109 216.694V215.998C644.109 211.126 651.069 209.038 651.069 200.86V148.312H639.585C637.497 148.312 635.583 146.572 635.583 144.31V140.482C635.583 138.22 637.497 136.48 639.585 136.48H651.069V129.52C651.069 108.292 669.165 92.806 698.745 92.806C725.367 92.806 739.809 104.638 739.809 118.384C739.809 124.3 734.763 129.346 727.977 129.346C706.923 129.346 710.403 101.506 695.265 101.506C683.259 101.506 678.909 117.688 680.823 134.392V136.48H699.963C702.225 136.48 703.791 138.22 703.791 140.482V144.31C703.791 146.572 702.225 148.312 699.963 148.312H680.823V200.86C680.823 209.038 690.219 211.126 690.219 215.998V216.694C690.219 218.782 688.653 220 686.217 220H648.111ZM711.795 216.694V215.998C711.795 210.952 718.755 208.864 718.755 200.86V167.8C718.755 159.796 711.795 157.36 711.795 153.184V152.488C711.795 150.574 713.361 149.704 715.797 148.486L742.245 135.61C747.117 133.174 750.075 135.958 750.075 139.264V200.86C750.075 208.864 757.905 210.952 757.905 215.998V216.694C757.905 218.782 756.165 220 753.555 220H715.971C713.535 220 711.795 218.782 711.795 216.694ZM827.271 220.174C824.835 220.174 823.095 218.956 823.095 216.868V216.172C823.095 211.126 829.881 209.038 829.359 201.034L827.619 169.888C826.749 152.662 823.443 146.224 815.613 146.224C807.957 146.224 804.303 153.01 804.303 163.102V201.034C804.303 209.038 812.133 211.126 812.133 216.172V216.868C812.133 218.956 810.393 220.174 807.783 220.174H770.199C767.763 220.174 766.023 218.956 766.023 216.868V216.172C766.023 211.126 773.679 209.038 773.679 201.034V166.756C773.679 158.404 764.631 157.36 764.631 152.314V151.792C764.631 149.704 766.197 148.66 768.633 147.442L792.993 135.436C797.343 133.174 799.605 136.132 799.605 139.612V147.964C804.129 139.612 813.003 134.74 824.661 134.74C839.799 134.74 855.633 143.266 857.721 170.932L859.983 201.034C860.679 209.038 866.247 211.126 866.247 216.172V216.868C866.247 218.956 864.507 220.174 862.071 220.174H827.271ZM913.599 221.74C892.545 221.74 872.535 206.776 872.535 178.24C872.535 152.314 891.849 134.74 913.773 134.74C921.081 134.74 926.997 136.48 931.695 139.612V116.47C931.695 108.292 922.473 107.248 922.473 102.202V101.68C922.473 99.766 924.039 97.852 926.475 97.156L953.619 88.978C958.665 87.412 961.275 88.456 961.275 93.154V201.034C961.275 209.038 968.235 211.126 968.235 215.998V216.694C968.235 218.782 966.669 220 964.233 220H939.351C936.567 220 934.827 218.26 934.827 215.65V214.084C929.607 218.956 922.125 221.74 913.599 221.74ZM902.289 164.668C901.767 179.284 907.509 212.692 920.559 213.214C926.475 213.388 931.695 207.994 931.695 198.598V165.016C931.695 153.88 924.039 143.266 916.035 143.266C907.509 143.266 902.811 150.748 902.289 164.668Z"
                                fill="black"></path>
                            <path
                                d="M680.812 370.74C673.504 370.74 667.762 369 663.064 365.868V386.748C663.064 394.752 670.72 396.84 670.72 401.712V402.408C670.72 404.496 669.154 405.714 666.544 405.714H629.83C627.22 405.714 625.654 404.496 625.654 402.408V401.712C625.654 396.84 632.614 394.752 632.614 386.748V315.408C632.614 307.926 624.088 307.056 624.088 302.01V301.14C624.088 299.052 625.654 297.486 628.09 296.094L651.058 284.784C656.452 282.348 658.366 284.784 658.366 288.264V293.484C662.716 287.22 670.72 283.74 680.638 283.74C700.3 283.74 721.702 297.486 721.702 325.848C721.702 353.34 702.388 370.74 680.812 370.74ZM663.064 337.506C663.064 352.296 670.372 362.214 678.028 362.214C686.728 362.214 691.252 354.558 691.252 340.29C691.252 321.498 686.206 292.266 673.504 292.266C667.936 292.266 663.934 296.616 663.064 303.228V337.506ZM773.676 370.74C747.75 370.74 729.48 352.992 729.48 326.718C729.48 300.792 749.49 283.914 772.632 283.74C793.338 283.566 807.258 293.658 807.258 308.97C807.258 321.15 795.774 331.242 779.418 333.852C773.328 334.896 767.238 335.244 762.192 335.07C766.716 343.77 774.198 349.164 783.942 349.164C792.642 349.164 799.428 345.684 802.56 341.508C804.996 339.072 809.172 340.116 808.998 343.944C808.65 353.514 798.558 370.74 773.676 370.74ZM757.146 312.45C757.146 317.148 757.668 321.672 758.712 325.848C762.018 326.022 765.324 325.848 767.412 325.5C775.068 324.108 779.244 318.714 779.244 306.708C779.244 299.052 774.894 292.962 769.152 292.962C762.018 292.962 757.146 300.966 757.146 312.45ZM822.566 369C820.13 369 818.564 367.782 818.564 365.694V364.998C818.564 360.126 825.524 358.038 825.524 350.034V315.408C825.524 307.23 816.998 306.534 816.998 301.488V300.966C816.998 298.878 818.39 297.312 821 295.92L845.708 284.436C850.232 282.348 851.798 284.784 851.798 288.264V301.314C855.452 290.004 863.63 283.74 875.984 283.74C886.25 283.74 892.166 291.222 892.166 300.966C892.166 309.666 889.034 317.322 878.942 317.322C862.934 317.322 870.068 300.966 861.368 300.966C855.8 300.966 854.93 310.014 854.93 317.67V350.034C854.93 358.038 864.152 360.126 864.152 364.998V365.694C864.152 367.782 862.586 369 859.976 369H822.566ZM906.415 369C903.979 369 902.413 367.782 902.413 365.694V364.998C902.413 360.126 909.373 358.038 909.373 349.86V297.312H897.889C895.801 297.312 893.887 295.572 893.887 293.31V289.482C893.887 287.22 895.801 285.48 897.889 285.48H909.373V276.78C909.373 257.466 920.161 241.806 945.391 241.806C960.703 241.806 973.231 252.072 973.231 263.904C973.231 268.602 969.577 274.344 961.921 274.344C941.389 274.344 951.481 250.158 938.953 250.158C926.077 250.158 933.907 277.128 938.605 285.48H958.267C960.529 285.48 962.095 287.22 962.095 289.482V293.31C962.095 295.572 960.529 297.312 958.267 297.312H939.301V349.86C939.301 358.038 948.697 360.126 948.697 364.998V365.694C948.697 367.782 947.131 369 944.695 369H906.415ZM1006.13 370.74C980.203 370.74 961.933 352.992 961.933 326.718C961.933 300.792 981.943 283.914 1005.09 283.74C1025.79 283.566 1039.71 293.658 1039.71 308.97C1039.71 321.15 1028.23 331.242 1011.87 333.852C1005.78 334.896 999.691 335.244 994.645 335.07C999.169 343.77 1006.65 349.164 1016.4 349.164C1025.1 349.164 1031.88 345.684 1035.01 341.508C1037.45 339.072 1041.63 340.116 1041.45 343.944C1041.1 353.514 1031.01 370.74 1006.13 370.74ZM989.599 312.45C989.599 317.148 990.121 321.672 991.165 325.848C994.471 326.022 997.777 325.848 999.865 325.5C1007.52 324.108 1011.7 318.714 1011.7 306.708C1011.7 299.052 1007.35 292.962 1001.61 292.962C994.471 292.962 989.599 300.966 989.599 312.45ZM1094.34 370.74C1067.03 370.74 1049.1 349.86 1049.1 327.066C1049.1 299.922 1069.64 283.914 1093.3 283.74C1113.66 283.566 1130.36 294.006 1130.36 309.492C1130.36 314.712 1127.06 319.932 1117.66 319.584C1099.91 318.54 1101.48 292.092 1088.6 292.266C1081.29 292.44 1076.42 301.14 1076.42 311.754C1076.42 334.374 1087.56 349.338 1104.78 349.338C1114.53 349.338 1120.44 344.118 1124.1 339.246C1126.36 336.462 1130.71 337.332 1130.71 341.16C1130.19 356.298 1118.18 370.74 1094.34 370.74ZM1174.52 370.74C1157.46 370.74 1146.15 359.604 1146.15 338.55V297.312H1139.72C1137.45 297.312 1135.71 295.572 1135.71 293.31V289.482C1135.71 287.046 1137.28 285.48 1139.72 285.48H1143.02C1153.64 285.48 1161.81 278.52 1164.08 267.906C1164.77 265.122 1166.69 263.382 1168.77 263.382H1172.95C1175.73 263.382 1177.47 265.122 1177.47 267.906V285.48H1195.57C1197.66 285.48 1199.57 287.22 1199.57 289.482V293.31C1199.57 295.572 1197.66 297.312 1195.57 297.312H1177.47V339.072C1177.47 344.988 1180.95 348.468 1185.48 348.468C1192.09 348.468 1195.05 345.162 1196.79 342.03C1199.22 338.898 1203.4 339.942 1203.4 343.248C1203.4 356.646 1193.66 370.74 1174.52 370.74Z"
                                fill="black"></path>
                            <path
                                d="M44.544 403.958C24.708 403.958 6.264 394.736 6.264 379.25C6.264 372.986 10.788 367.766 18.618 367.766C36.54 367.766 31.146 395.258 47.676 395.606C55.332 395.78 61.422 388.124 61.422 363.068V362.894C56.55 366.896 49.764 369.158 40.542 369.158C24.36 369.158 9.222 356.63 9.222 336.62V307.562C9.222 299.384 2.262 297.296 2.262 292.946V292.25C2.262 290.336 3.828 288.596 6.264 288.248L32.19 284.768C37.236 284.072 40.368 285.116 40.368 288.248L39.846 339.752C39.672 352.28 43.5 357.674 49.764 357.674C56.376 357.674 61.422 350.888 61.422 341.84V307.562C61.422 299.384 54.288 297.296 54.288 292.946V292.25C54.288 290.336 55.854 288.596 58.29 288.248L84.216 284.594C89.436 283.898 91.872 285.116 91.872 288.248V358.196C91.872 388.994 69.774 403.958 44.544 403.958ZM151.766 370.898C125.144 370.898 103.568 352.454 103.568 327.224C103.568 301.472 125.666 283.898 150.722 283.898C176.822 283.898 198.398 301.994 198.398 327.572C198.398 352.976 177.344 370.898 151.766 370.898ZM134.366 314.174C134.366 328.268 141.5 362.372 155.594 362.372C163.598 362.372 166.556 354.02 166.556 340.97C166.556 327.398 159.596 292.424 145.85 292.424C137.324 292.424 134.366 300.08 134.366 314.174ZM243.971 370.898C226.397 370.898 211.433 358.892 211.433 336.62V307.562C211.433 299.384 204.473 297.296 204.473 292.946V292.25C204.473 290.336 206.039 288.596 208.475 288.248L234.401 284.768C239.447 284.072 242.579 285.116 242.579 288.248L242.057 339.752C241.883 354.02 245.537 359.414 253.193 359.414C259.631 359.414 264.677 352.628 264.677 342.014V307.562C264.677 299.384 257.717 297.296 257.717 292.946V292.25C257.717 290.336 259.283 288.596 261.719 288.248L287.645 284.768C292.691 284.072 295.301 285.116 295.301 288.248V350.018C295.301 364.112 302.783 357.326 302.783 364.46C302.783 369.158 295.997 370.202 284.861 370.202C274.073 370.202 269.375 367.592 268.505 360.11C263.981 367.07 255.803 370.898 243.971 370.898ZM315.603 369.158C313.167 369.158 311.601 367.94 311.601 365.852V365.156C311.601 360.284 318.561 358.196 318.561 350.192V315.566C318.561 307.388 310.035 306.692 310.035 301.646V301.124C310.035 299.036 311.427 297.47 314.037 296.078L338.745 284.594C343.269 282.506 344.835 284.942 344.835 288.422V301.472C348.489 290.162 356.667 283.898 369.021 283.898C379.287 283.898 385.203 291.38 385.203 301.124C385.203 309.824 382.071 317.48 371.979 317.48C355.971 317.48 363.105 301.124 354.405 301.124C348.837 301.124 347.967 310.172 347.967 317.828V350.192C347.967 358.196 357.189 360.284 357.189 365.156V365.852C357.189 367.94 355.623 369.158 353.013 369.158H315.603Z"
                                fill="black"></path>
                            <path
                                d="M625.148 524.74C617.84 524.74 612.098 523 607.4 519.868V540.748C607.4 548.752 615.056 550.84 615.056 555.712V556.408C615.056 558.496 613.49 559.714 610.88 559.714H574.166C571.556 559.714 569.99 558.496 569.99 556.408V555.712C569.99 550.84 576.95 548.752 576.95 540.748V469.408C576.95 461.926 568.424 461.056 568.424 456.01V455.14C568.424 453.052 569.99 451.486 572.426 450.094L595.394 438.784C600.788 436.348 602.702 438.784 602.702 442.264V447.484C607.052 441.22 615.056 437.74 624.974 437.74C644.636 437.74 666.038 451.486 666.038 479.848C666.038 507.34 646.724 524.74 625.148 524.74ZM607.4 491.506C607.4 506.296 614.708 516.214 622.364 516.214C631.064 516.214 635.588 508.558 635.588 494.29C635.588 475.498 630.542 446.266 617.84 446.266C612.272 446.266 608.27 450.616 607.4 457.228V491.506ZM679.733 523C677.297 523 675.731 521.782 675.731 519.694V518.998C675.731 514.126 682.691 512.038 682.691 504.034V469.408C682.691 461.23 674.165 460.534 674.165 455.488V454.966C674.165 452.878 675.557 451.312 678.167 449.92L702.875 438.436C707.399 436.348 708.965 438.784 708.965 442.264V455.314C712.619 444.004 720.797 437.74 733.151 437.74C743.417 437.74 749.333 445.222 749.333 454.966C749.333 463.666 746.201 471.322 736.109 471.322C720.101 471.322 727.235 454.966 718.535 454.966C712.967 454.966 712.097 464.014 712.097 471.67V504.034C712.097 512.038 721.319 514.126 721.319 518.998V519.694C721.319 521.782 719.753 523 717.143 523H679.733ZM800.344 524.74C773.722 524.74 752.146 506.296 752.146 481.066C752.146 455.314 774.244 437.74 799.3 437.74C825.4 437.74 846.976 455.836 846.976 481.414C846.976 506.818 825.922 524.74 800.344 524.74ZM782.944 468.016C782.944 482.11 790.078 516.214 804.172 516.214C812.176 516.214 815.134 507.862 815.134 494.812C815.134 481.24 808.174 446.266 794.428 446.266C785.902 446.266 782.944 453.922 782.944 468.016ZM893.071 524.74C878.107 524.74 860.185 517.78 860.185 486.982V461.404C860.185 453.226 853.225 451.138 853.225 446.788V446.092C853.225 444.178 854.791 442.438 857.227 442.09L882.979 438.61C888.199 437.914 891.331 438.958 891.331 442.09L890.809 496.03C890.635 508.732 893.593 513.082 900.379 513.256C914.299 513.778 925.957 493.768 925.957 478.804C925.957 464.014 909.253 464.884 909.253 449.92C909.253 443.134 913.951 437.914 922.477 437.914C933.265 437.914 941.269 446.266 941.269 464.536C941.269 500.206 921.433 524.74 893.071 524.74ZM954.824 523C952.388 523 950.648 521.782 950.648 519.694V518.998C950.648 513.952 957.608 511.864 957.608 503.86V470.8C957.608 462.796 950.648 460.36 950.648 456.184V455.488C950.648 453.574 952.214 452.704 954.65 451.486L980.924 438.61C985.796 436.174 988.754 438.958 988.754 442.264V503.86C988.754 511.864 996.584 513.952 996.584 518.998V519.694C996.584 521.782 994.844 523 992.408 523H954.824ZM953.432 411.814C953.432 401.896 961.436 394.414 973.442 394.414C985.274 394.414 993.278 401.896 993.278 411.814C993.278 421.558 985.274 429.214 973.442 429.214C961.436 429.214 953.432 421.558 953.432 411.814ZM1044.7 524.74C1023.65 524.74 1003.64 509.776 1003.64 481.24C1003.64 455.314 1022.95 437.74 1044.88 437.74C1052.18 437.74 1058.1 439.48 1062.8 442.612V419.47C1062.8 411.292 1053.58 410.248 1053.58 405.202V404.68C1053.58 402.766 1055.14 400.852 1057.58 400.156L1084.72 391.978C1089.77 390.412 1092.38 391.456 1092.38 396.154V504.034C1092.38 512.038 1099.34 514.126 1099.34 518.998V519.694C1099.34 521.782 1097.77 523 1095.34 523H1070.45C1067.67 523 1065.93 521.26 1065.93 518.65V517.084C1060.71 521.956 1053.23 524.74 1044.7 524.74ZM1033.39 467.668C1032.87 482.284 1038.61 515.692 1051.66 516.214C1057.58 516.388 1062.8 510.994 1062.8 501.598V468.016C1062.8 456.88 1055.14 446.266 1047.14 446.266C1038.61 446.266 1033.91 453.748 1033.39 467.668ZM1150.46 524.74C1124.54 524.74 1106.27 506.992 1106.27 480.718C1106.27 454.792 1126.28 437.914 1149.42 437.74C1170.13 437.566 1184.05 447.658 1184.05 462.97C1184.05 475.15 1172.56 485.242 1156.21 487.852C1150.12 488.896 1144.03 489.244 1138.98 489.07C1143.5 497.77 1150.99 503.164 1160.73 503.164C1169.43 503.164 1176.22 499.684 1179.35 495.508C1181.78 493.072 1185.96 494.116 1185.79 497.944C1185.44 507.514 1175.35 524.74 1150.46 524.74ZM1133.93 466.45C1133.93 471.148 1134.46 475.672 1135.5 479.848C1138.81 480.022 1142.11 479.848 1144.2 479.5C1151.86 478.108 1156.03 472.714 1156.03 460.708C1156.03 453.052 1151.68 446.962 1145.94 446.962C1138.81 446.962 1133.93 454.966 1133.93 466.45ZM1199.35 523C1196.92 523 1195.35 521.782 1195.35 519.694V518.998C1195.35 514.126 1202.31 512.038 1202.31 504.034V469.408C1202.31 461.23 1193.79 460.534 1193.79 455.488V454.966C1193.79 452.878 1195.18 451.312 1197.79 449.92L1222.5 438.436C1227.02 436.348 1228.59 438.784 1228.59 442.264V455.314C1232.24 444.004 1240.42 437.74 1252.77 437.74C1263.04 437.74 1268.95 445.222 1268.95 454.966C1268.95 463.666 1265.82 471.322 1255.73 471.322C1239.72 471.322 1246.86 454.966 1238.16 454.966C1232.59 454.966 1231.72 464.014 1231.72 471.67V504.034C1231.72 512.038 1240.94 514.126 1240.94 518.998V519.694C1240.94 521.782 1239.37 523 1236.76 523H1199.35Z"
                                fill="black"></path>
                            <g filter="url(#filter0_d_10240_62)">
                                <path
                                    d="M485.986 60.1748L439.366 231.743L585.27 267.837L626.667 105.012C668.494 116.251 667.001 118.243 668.167 111.366C673.673 78.9045 657.751 76.7811 648.877 74.0511C613.013 63.0175 537.6 40.3428 522.859 37.9135C498.107 33.8344 490.48 48.2039 485.986 60.1748Z"
                                    fill="#F8F4E6" stroke="black" stroke-width="9.30589"></path>
                                <path
                                    d="M623.345 104.112L539.229 81.3878C543.558 69.6988 545.706 42.0601 520.383 37.5093"
                                    stroke="black" stroke-width="9.30589" stroke-linejoin="round"></path>
                                <path d="M499.887 107.475L593.452 133.36M493.622 128.311L587.186 154.196" stroke="black"
                                    stroke-width="7.58632" stroke-linecap="round"></path>
                                <path
                                    d="M507.11 625.241L343.471 583.082C328.964 579.362 319.901 564.293 323.367 549.516L398.046 226.7C401.439 211.95 416.043 202.956 430.577 206.751L594.216 248.911C608.723 252.631 617.785 267.7 614.32 282.476L539.641 605.293C536.175 620.069 521.644 629.036 507.11 625.241Z"
                                    fill="#F8D247" stroke="#060405" stroke-width="9.22258" stroke-miterlimit="10"
                                    stroke-linecap="round"></path>
                                <path
                                    d="M513.842 557.556L367.16 519.753C358.617 517.513 353.295 508.701 355.315 499.941L414.162 245.815C416.209 237.13 424.749 231.848 433.364 234.062L579.973 271.891C588.515 274.131 593.837 282.943 591.818 291.703L532.97 545.829C530.997 554.487 522.384 559.796 513.842 557.556Z"
                                    fill="white" stroke="#060405" stroke-width="9.22258" stroke-miterlimit="10"
                                    stroke-linecap="round"></path>
                                <path
                                    d="M542.474 405.022C550.015 372.436 526.088 338.274 489.032 328.717C451.975 319.16 415.821 337.829 408.28 370.414C400.739 402.999 424.665 437.162 461.722 446.719C498.779 456.276 534.932 437.607 542.474 405.022Z"
                                    fill="white" stroke="#060405" stroke-width="9.22258" stroke-miterlimit="10"
                                    stroke-linecap="round"></path>
                                <path
                                    d="M467.024 423.836C481.157 419.915 492.761 408.539 496.348 392.959C499.916 377.554 494.789 361.993 484.239 351.688"
                                    fill="white"></path>
                                <path
                                    d="M467.024 423.836C481.157 419.915 492.761 408.539 496.348 392.959C499.916 377.554 494.789 361.993 484.239 351.688"
                                    stroke="#060405" stroke-width="9.22258" stroke-miterlimit="10"
                                    stroke-linecap="round"></path>
                                <path
                                    d="M462.217 408.923C471.266 406.416 478.732 399.07 481.028 389.027C483.306 379.16 480.005 369.11 473.258 362.503"
                                    fill="white"></path>
                                <path
                                    d="M462.217 408.923C471.266 406.416 478.732 399.07 481.028 389.027C483.306 379.16 480.005 369.11 473.258 362.503"
                                    stroke="#060405" stroke-width="9.22258" stroke-miterlimit="10"
                                    stroke-linecap="round"></path>
                                <path
                                    d="M453.647 396.804C459.094 395.259 463.543 390.948 464.917 384.957C466.318 379.042 464.33 373.082 460.245 369.063"
                                    fill="white"></path>
                                <path
                                    d="M453.647 396.804C459.094 395.259 463.543 390.948 464.917 384.957C466.318 379.042 464.33 373.082 460.245 369.063"
                                    stroke="#060405" stroke-width="9.22258" stroke-miterlimit="10"
                                    stroke-linecap="round"></path>
                            </g>
                            <defs>
                                <filter id="filter0_d_10240_62" x="316.845" y="26.9823" width="378.806" height="621.047"
                                    filterUnits="userSpaceOnUse" color-interpolation-filters="sRGB">
                                    <feFlood flood-opacity="0" result="BackgroundImageFix"></feFlood>
                                    <feColorMatrix in="SourceAlpha" type="matrix"
                                        values="0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 127 0" result="hardAlpha">
                                    </feColorMatrix>
                                    <feOffset dx="10.2641" dy="5.8652"></feOffset>
                                    <feGaussianBlur stdDeviation="5.71857"></feGaussianBlur>
                                    <feComposite in2="hardAlpha" operator="out"></feComposite>
                                    <feColorMatrix type="matrix" values="0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0.25 0">
                                    </feColorMatrix>
                                    <feBlend mode="normal" in2="BackgroundImageFix"
                                        result="effect1_dropShadow_10240_62"></feBlend>
                                    <feBlend mode="normal" in="SourceGraphic" in2="effect1_dropShadow_10240_62"
                                        result="shape"></feBlend>
                                </filter>
                            </defs>
                        </svg>
                    </div>
                    <div class="flex flex-col items-center mb-3">
                        <label class="container text-sm mb-3"> I confirm that I have read and understood your <a href=""
                                class="border-b border-solid border-black text-sm">terms & conditions</a> and <a href=""
                                class="border-b border-solid border-black text-sm">privacy policy</a>
                            <input type="checkbox">
                            <span class="checkmark"></span>
                        </label>

                        <label class="container text-sm">I agree to receive occasional marketing communications,
                            including a reminder when my contract is due for renewal.
                            <input type="checkbox">
                            <span class="checkmark"></span>
                        </label>

                    </div>

                    <button
                        class="w-full rounded-[3px] text-[21px] h-[48px] bg-[#f7d147] flex items-center justify-center ml-auto mt-2 rounded-sm font-medium">Next
                        step: Compare</button>
                    <div class="text-center text-black/30 text-sm"><span class="font-bold">I understand that Tuza is a
                            free</span> service and that Tuza may receive commission from providers. <span
                            class="font-bold">This does not impact the recommendations or sorting of providers.</span>
                    </div>
                </div>
            </div>
        </div>

    </transition>

</template>
<script>
import Header from '../components/Header.vue';
import RadioButton from '~/components/RadioButton.vue';

export default {
    components: {
        Header,
        RadioButton
    },
    data() {
        return {
            activeProvider: null,
            showFullList: false,
            showToolTip: false,
            currentIndex: 0,
            tempIndex: 0,
            activeBlocks: [0]
        };
    },
    methods: {
        

        firstBlock() {
            this.activeBlocks.push(1);
            this.$nextTick(() => {
                const container = document.querySelector('#containerT');
                console.log(container)
                if (container) {
                    container.style.transition = "transform 2.5s"; // Устанавливаем transition
                    container.style.transform = "translateY(-520px)"; // Применяем translate
                }
            });


        },

        secondBlock() {
            this.activeBlocks.push(2);
            this.$nextTick(() => {
                const container = document.querySelector('#containerT');
                if (container) {
                    container.style.transition = "transform 2.5s";
                    container.style.transform = "translateY(-730px)";
                }
            });
        },

        thirdBlock () {
            this.activeBlocks.push(3);
            this.$nextTick(() => {
                const container = document.querySelector('#containerT');
                if (container) {
                    container.style.transition = "transform 2.5s";
                    container.style.transform = "translateY(-1045px)";
                }
            });
        },

        fourBlock () {
            this.activeBlocks.push(4);
            this.$nextTick(() => {
                const container = document.querySelector('#containerT');
                if (container) {
                    container.style.transition = "transform 2.5s";
                    container.style.transform = "translateY(-1465px)";
                }
            });
        },

        fiveBlock () {
            this.activeBlocks.push(5);
            this.$nextTick(() => {
                const container = document.querySelector('#containerT');
                if (container) {
                    container.style.transition = "transform 2.5s";
                    container.style.transform = "translateY(-1735px)";
                }
            });
        },

        sixBlock () {
            this.activeBlocks.push(6);
            this.$nextTick(() => {
                const container = document.querySelector('#containerT');
                if (container) {
                    container.style.transition = "transform 2.5s";
                    container.style.transform = "translateY(-1935px)";
                }
            });
        },
        sevenBlock () {
            this.activeBlocks.push(7);
            this.$nextTick(() => {
                const container = document.querySelector('#containerT');
                if (container) {
                    container.style.transition = "transform 2.5s";
                    container.style.transform = "translateY(-2195px)";
                }
            });
        },
        eightBlock () {
            this.activeBlocks.push(8);
            this.$nextTick(() => {
                const container = document.querySelector('#containerT');
                if (container) {
                    container.style.transition = "transform 2.5s";
                    container.style.transform = "translateY(-2465px)";
                }
            });
        },

        nineBlock () {
            this.activeBlocks.push(9);
            this.$nextTick(() => {
                const container = document.querySelector('#containerT');
                if (container) {
                    container.style.transition = "transform 2.5s";
                    container.style.transform = "translateY(-2745px)";
                }
            });
        },

        tenBlock () {
            this.activeBlocks.push(10);
            this.$nextTick(() => {
                const container = document.querySelector('#containerT');
                if (container) {
                    container.style.transition = "transform 2.5s";
                    container.style.transform = "translateY(-3185px)";
                }
            });
        },

        elevenBlock () {
            this.activeBlocks.push(11);
            this.$nextTick(() => {
                const container = document.querySelector('#containerT');
                if (container) {
                    container.style.transition = "transform 2.5s";
                    container.style.transform = "translateY(-3435px)";
                }
            });
        },

        twelveBlock () {
            this.activeBlocks.push(12);
            this.$nextTick(() => {
                const container = document.querySelector('#containerT');
                if (container) {
                    container.style.transition = "transform 2.5s";
                    container.style.transform = "translateY(-3695px)";
                }
            });
        }
    }
};
</script>


<style scoped>
.recolleta {
    font-family: "Recoletta-Regular", sans-serif;
    font-weight: 400;
}



[type="radio"]:checked,
[type="radio"]:not(:checked) {
    position: absolute;
    left: -9999px;
}

[type="radio"]:checked+label,
[type="radio"]:not(:checked)+label {
    position: relative;
    cursor: pointer;
    line-height: 20px;
    display: inline-block;
    color: #666;
    border: 1px solid #a49d7d33;
    width: 292px;
    height: 79px;
    border-radius: 12px;
    margin-right: 10px;
    display: flex;
    justify-content: center;
    align-items: center;
    font-size: 20px
}

[type="radio"]:not(:checked):hover+label {
    border: 1px solid #000;
}

[type="radio"]:checked+label {
    border: 1px solid #000;
    font-weight: 500;
    color: #000;
}

[type="radio"]:not(:checked):hover label::after {
    background: red
}

[type="radio"]:not(:checked):hover+label[data-v-02281a80]:after {
    opacity: 1;
    transform: scale(1);
}

[type="radio"]:checked+label:before,
[type="radio"]:not(:checked)+label:before {
    content: '';
    position: absolute;
    left: 40px;
    top: calc(50% - 12px);
    width: 24px;
    height: 24px;
    border: 2px solid #000;
    border-radius: 100%;
    background: #fff;
}

[type="radio"]:checked+label:after,
[type="radio"]:not(:checked)+label:after {
    content: '';
    width: 14px;
    height: 14px;
    background: #f7d147;
    position: absolute;
    top: 32px;
    left: 45px;
    border-radius: 100%;
    -webkit-transition: all 0.2s ease;
    transition: all 0.2s ease;
}

[type="radio"]:not(:checked)+label:after {
    opacity: 0;
    -webkit-transform: scale(0);
    transform: scale(0);
}

[type="radio"]:checked+label:after {
    opacity: 1;
    -webkit-transform: scale(1);
    transform: scale(1);
}

.active {
    border: 1px solid black
}


.container {
    display: block;
    position: relative;
    padding-left: 35px;
    margin-bottom: 12px;
    cursor: pointer;
    -webkit-user-select: none;
    -moz-user-select: none;
    -ms-user-select: none;
    user-select: none;
}

/* Hide the browser's default checkbox */
.container input {
    position: absolute;
    opacity: 0;
    cursor: pointer;
    height: 0;
    width: 0;
}

/* Create a custom checkbox */
.checkmark {
    position: absolute;
    top: 0;
    left: 0;
    height: 20px;
    width: 20px;
    border-radius: 3px;
    background-color: #eee;
}

/* On mouse-over, add a grey background color */
.container:hover input~.checkmark {
    background-color: #ccc;
}

/* When the checkbox is checked, add a blue background */
.container input:checked~.checkmark {
    background-color: #f7d147;
}

/* Create the checkmark/indicator (hidden when not checked) */
.checkmark:after {
    content: "";
    position: absolute;
    display: none;
}

/* Show the checkmark when checked */
.container input:checked~.checkmark:after {
    display: block;
}

/* Style the checkmark/indicator */
.container .checkmark:after {
    left: 7px;
    top: 4px;
    width: 5px;
    height: 10px;
    border: solid white;
    border-width: 0 3px 3px 0;
    -webkit-transform: rotate(45deg);
    -ms-transform: rotate(45deg);
    transform: rotate(45deg);
}


#containerT {
    overflow: hidden;
}


.slide-fade-enter-active,
.slide-fade-leave-active {
    transition: opacity 1s, transform 1s;
}

.slide-fade-enter-to,
.slide-fade-leave-from {
    opacity: 1;
    transform: translateY(0);
}

.slide-fade-enter-to+.block {
    transform: translateY(calc(100% - 2px));
}

.slide-fade-leave-from+.block {
    transition: transform 1s;
    transform: translateY(-100%);
}

.block:not(:first-child) {
    animation: rollUp 0.5s forwards;
}

@keyframes rollUp {
    0% {
        transform: translateY(100vh);
    }

    100% {
        transform: translateY(0);
    }
}



.fadeIn {
    animation: rollUp 2s
}
</style>
