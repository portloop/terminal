<template>
    <div class="flex relative z-1 mt-[161px] flex col justify-center h-full items-center">
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
                <div class="flex items-center mb-4"><svg xmlns="http://www.w3.org/2000/svg" width="24px" height="24px"
                        viewBox="0 0 24 24" fill="none">
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
                <div class="text-[20px] recolleta">"Very good advice freely given that helped me make the decision that
                    was best for me"</div>
                <div class="flex items-center justify-between">
                    <div class="text-sm flex flex-col">
                        <div class="text-black/50">Trustpilot</div>
                        <div class="font-light">Ruth Tesdale</div>
                    </div>
                    <img src="https://quotes.tuza.co.uk/assets/trustpilot-f26bd861.svg" />
                </div>
            </div>
            <button @click="$emit('next')" class="w-[65px] h-[34px] bg-[#f7d147] flex items-center justify-center ml-auto mt-2 rounded-sm font-medium">Next</button>
    
        </div>
    </div>
</template>
<script>
export default {
    
}
</script>
<style scoped>
.block {
    opacity: 0;
    transform: translateY(100px);
    transition: opacity 0.5s, transform 0.5s;
  }
  .block.enter-active, .block.leave-active {
    transition: opacity 0.5s, transform 0.5s;
  }
  .block.enter-from, .block.leave-to {
    opacity: 0;
    transform: translateY(100px);
  }
  .block.enter-to, .block.leave-from {
    opacity: 1;
    transform: translateY(0);
  }
</style>