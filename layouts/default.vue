<template>
  <div class="pt-16">
    <div
      class="header fixed top-0 z-40 w-full border-b dark:border-gray-800 bg-white dark:bg-gray-900"
    >
      <div class="container mx-auto px-4 lg:px-8 flex-1">
        <div class="flex items-center justify-between h-16">
          <div class="w-1/6">
            <a
              href="/"
              aria-current="page"
              class="text-xl tracking-tight flex items-center flex-shrink-0 nuxt-link-exact-active nuxt-link-active"
              style="width:104px"
              >Cade a loja?</a
            >
          </div>
          <div
            class="hidden flex-1 lg:flex justify-center ml-4 mr-2 lg:mx-8 w-4/6"
          >
            <div class="w-full relative flex flex-col justify-between">
              <div class="w-full relative">
                <label for="search" class="sr-only">Buscar</label>
                <div class="relative">
                  <div
                    class="absolute inset-y-0 left-0 pl-3 flex items-center pointer-events-none"
                  >
                    <svg
                      fill="none"
                      stroke="currentColor"
                      stroke-linecap="round"
                      stroke-linejoin="round"
                      stroke-width="2"
                      viewBox="0 0 24 24"
                      class="h-5 w-5 text-gray-500"
                    >
                      <path
                        d="M21 21l-6-6m2-5a7 7 0 11-14 0 7 7 0 0114 0z"
                      ></path>
                    </svg>
                  </div>
                  <input
                    id="search"
                    placeholder="Procure qualquer tipo de coisa aqui!"
                    type="search"
                    autocomplete="off"
                    class="block w-full pl-10 pr-3 py-2 truncate leading-5 placeholder-gray-500 border border-transparent text-gray-700 dark:text-white dark-focus:text-white focus:border-gray-300 dark-focus:border-gray-700 rounded-md focus:outline-none focus:bg-white dark-focus:bg-gray-900 bg-gray-200 dark:bg-gray-800"
                  />
                </div>
              </div>
              <ul
                class="z-10 absolute w-full flex-1 top-0 bg-white dark:bg-gray-900 rounded-md border border-gray-300 dark:border-gray-700 overflow-hidden"
                style="margin-top:37px;display:none"
              >
                <!---->
              </ul>
            </div>
          </div>
          <div class="flex items-center justify-end w-1/6">
            <a
              href="https://twitter.com/haykou182"
              target="_blank"
              rel="noopener noreferrer"
              title="Twitter"
              name="Twitter"
              class="hidden lg:block hover:text-green-500 mr-2"
              ><svg
                width="24"
                height="24"
                viewBox="0 0 24 24"
                fill="currentColor"
                xmlns="http://www.w3.org/2000/svg"
                class="w-6 h-6"
              >
                <path
                  d="M22 5.89584C21.2498 6.22182 20.456 6.43658 19.6438 6.53334C20.4974 6.0335 21.1393 5.23941 21.4492 4.30001C20.6421 4.77192 19.7606 5.10304 18.8425 5.27917C18.4559 4.87398 17.9909 4.55163 17.4758 4.33173C16.9607 4.11183 16.4063 3.99897 15.8463 4.00001C13.5788 4.00001 11.7438 5.80834 11.7438 8.0375C11.7421 8.34757 11.7777 8.65672 11.8496 8.95833C10.2236 8.88211 8.63147 8.46733 7.17499 7.74053C5.71852 7.01372 4.42979 5.9909 3.39125 4.73751C3.02691 5.35172 2.83422 6.05252 2.83333 6.76667C2.83333 8.16667 3.56375 9.40417 4.66667 10.1292C4.01322 10.1137 3.37316 9.94071 2.80083 9.625V9.675C2.80083 11.6333 4.2175 13.2625 6.0925 13.6333C5.73991 13.7273 5.37657 13.7749 5.01167 13.775C4.75274 13.7754 4.4944 13.7503 4.24042 13.7C4.76167 15.3042 6.27875 16.4708 8.07583 16.5042C6.61557 17.6295 4.82276 18.2378 2.97917 18.2333C2.65192 18.2328 2.32499 18.2134 2 18.175C3.87549 19.3726 6.0556 20.006 8.28083 20C15.8375 20 19.9658 13.8458 19.9658 8.50833C19.9658 8.33333 19.9613 8.15834 19.9529 7.9875C20.7542 7.41753 21.4474 6.70922 22 5.89584V5.89584Z"
                ></path></svg
            ></a>
            <a
              href="https://github.com/heliomsolivas/cade-a-loja"
              target="_blank"
              rel="noopener noreferrer"
              title="Github"
              name="Github"
              class="hidden lg:block hover:text-green-500 mr-4"
              ><svg
                width="24"
                height="24"
                viewBox="0 0 24 24"
                fill="currentColor"
                xmlns="http://www.w3.org/2000/svg"
                class="w-6 h-6"
              >
                <path
                  d="M12 2C6.47768 2 2 6.59375 2 12.2545C2 16.7857 4.86607 20.625 8.83929 21.9821C8.89502 21.9942 8.9519 22.0002 9.00893 22C9.37946 22 9.52232 21.7277 9.52232 21.4911C9.52232 21.2455 9.51339 20.6027 9.50893 19.7455C9.17814 19.8231 8.83974 19.8635 8.5 19.8661C6.57589 19.8661 6.13839 18.3705 6.13839 18.3705C5.68304 17.1875 5.02679 16.8705 5.02679 16.8705C4.15625 16.2589 5.02232 16.2411 5.08929 16.2411H5.09375C6.09821 16.3304 6.625 17.3036 6.625 17.3036C7.125 18.1786 7.79464 18.4241 8.39286 18.4241C8.78841 18.4162 9.17784 18.3249 9.53571 18.1562C9.625 17.4955 9.88393 17.0446 10.1696 16.7857C7.95089 16.5268 5.61607 15.6473 5.61607 11.7187C5.61607 10.5982 6.00446 9.68303 6.64286 8.96875C6.54018 8.70982 6.19643 7.66518 6.74107 6.25446C6.81413 6.23698 6.88921 6.22947 6.96429 6.23214C7.32589 6.23214 8.14286 6.37053 9.49107 7.30803C11.1293 6.84969 12.8618 6.84969 14.5 7.30803C15.8482 6.37053 16.6652 6.23214 17.0268 6.23214C17.1019 6.22947 17.1769 6.23698 17.25 6.25446C17.7946 7.66518 17.4509 8.70982 17.3482 8.96875C17.9866 9.6875 18.375 10.6027 18.375 11.7187C18.375 15.6562 16.0357 16.5223 13.808 16.7768C14.1652 17.0937 14.4866 17.7187 14.4866 18.6741C14.4866 20.0446 14.4732 21.1518 14.4732 21.4866C14.4732 21.7277 14.6116 22 14.9821 22C15.0421 22.0003 15.102 21.9943 15.1607 21.9821C19.1384 20.625 22 16.7812 22 12.2545C22 6.59375 17.5223 2 12 2Z"
                ></path></svg
            ></a>
            <button
              aria-label="Hamburger Menu"
              class="lg:hidden p-2 pr-0 rounded-md hover:text-green-500 focus:outline-none focus:outline-none"
            >
              <svg
                stroke="currentColor"
                fill="none"
                viewBox="0 0 24 24"
                class="w-6 h-6"
              >
                <path
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  stroke-width="2"
                  d="M4 6h16M4 12h16M4 18h16"
                ></path>
              </svg>
            </button>
          </div>
        </div>
      </div>
    </div>
    <main class="container mx-auto px-4 lg:px-8">
      <nuxt />
    </main>
  </div>
</template>

<style>
.header {
  height: 64px;
}
html {
  font-family: 'Source Sans Pro', -apple-system, BlinkMacSystemFont, 'Segoe UI',
    Roboto, 'Helvetica Neue', Arial, sans-serif;
  font-size: 16px;
  word-spacing: 1px;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;
}

*,
*:before,
*:after {
  box-sizing: border-box;
  margin: 0;
}

.button--green {
  display: inline-block;
  border-radius: 4px;
  border: 1px solid #3b8070;
  color: #3b8070;
  text-decoration: none;
  padding: 10px 30px;
}

.button--green:hover {
  color: #fff;
  background-color: #3b8070;
}

.button--grey {
  display: inline-block;
  border-radius: 4px;
  border: 1px solid #35495e;
  color: #35495e;
  text-decoration: none;
  padding: 10px 30px;
  margin-left: 15px;
}

.button--grey:hover {
  color: #fff;
  background-color: #35495e;
}
</style>
