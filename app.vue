<script>
export default {
  mounted() {
    // Vérifiez si le code s'exécute côté client (dans le navigateur)
    if (process.client) {
      // Placez votre code qui utilise "document" ici
      const scrollContainer = document.getElementById("scrollContainer");

      let isScrolling = false;
      let startX, scrollLeft;

      // Événement de clic de souris
      scrollContainer.addEventListener("mousedown", (e) => {
        isScrolling = true;
        startX = e.pageX - scrollContainer.offsetLeft;
        scrollLeft = scrollContainer.scrollLeft;
        scrollContainer.style.cursor = "grabbing";
      });

      // Événement de relâchement de souris
      scrollContainer.addEventListener("mouseup", () => {
        isScrolling = false;
        scrollContainer.style.cursor = "auto";
      });

      // Événement de mouvement de souris
      scrollContainer.addEventListener("mousemove", (e) => {
        if (!isScrolling) return;
        e.preventDefault();
        const x = e.pageX - scrollContainer.offsetLeft;
        const walk = (x - startX) * 1;
        scrollContainer.scrollLeft = scrollLeft - walk;
      });

      // Événements tactiles
      scrollContainer.addEventListener("touchstart", (e) => {
        isScrolling = true;
        startX = e.touches[0].pageX - scrollContainer.offsetLeft;
        scrollLeft = scrollContainer.scrollLeft;
      });

      scrollContainer.addEventListener("touchmove", (e) => {
        if (!isScrolling) return;
        e.preventDefault();
        const x = e.touches[0].pageX - scrollContainer.offsetLeft;
        const walk = (x - startX) * 1;
        scrollContainer.scrollLeft = scrollLeft - walk;
      });

      scrollContainer.addEventListener("touchend", () => {
        isScrolling = false;
      });
    }
  },
};
</script>

<template>
  <head>
    <title>Youtube</title>
  </head>
  <div>
    <nav
      class="flex font-bold items-center mt-1 h-12 bg-neutral-950 justify-between"
    >
      <div class="flex items-center gap-2">
        <button class="ml-5 text-white h-[40px] hidden md:block">
          <svg
            xmlns="http://www.w3.org/2000/svg"
            class="h-6 w-6"
            fill="none"
            viewBox="0 0 24 24"
            stroke="currentColor"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-width="2"
              d="M4 6h16M4 12h16M4 18h16"
            ></path>
          </svg>
        </button>
        <div class="flex ml-2 md:ml-0">
          <svg
            xmlns="http://www.w3.org/2000/svg"
            width="40"
            height="20"
            viewBox="0 0 256 180"
          >
            <path
              fill="red"
              d="M250.346 28.075A32.18 32.18 0 0 0 227.69 5.418C207.824 0 127.87 0 127.87 0S47.912.164 28.046 5.582A32.18 32.18 0 0 0 5.39 28.24c-6.009 35.298-8.34 89.084.165 122.97a32.18 32.18 0 0 0 22.656 22.657c19.866 5.418 99.822 5.418 99.822 5.418s79.955 0 99.82-5.418a32.18 32.18 0 0 0 22.657-22.657c6.338-35.348 8.291-89.1-.164-123.134Z"
            />
            <path
              fill="#FFF"
              d="m102.421 128.06l66.328-38.418l-66.328-38.418z"
            />
          </svg>
          <p class="text-white">YOUTUBE</p>
          *
        </div>
      </div>
      <div
        class="h-[40px] hidden md:flex rounded-full border-2 border-neutral-700 overflow-hidden bg-neutral-900"
      >
        <input
          class="hidden md:flex h-[40px] w-[35rem] bg-neutral-900 caret-white outline-0 text-white rounded-full ml-4 mt-[-3px]"
          placeholder="Rechercher"
          type="text"
        />
      </div>
      <div class="flex gap-7 mr-10">
        <svg
          class="text-white"
          width="23"
          height="23"
          viewBox="0 0 24 24"
          fill="none"
          xmlns="http://www.w3.org/2000/svg"
        >
          <path
            d="M11.0001 1H13.0001V15.4853L16.2428 12.2427L17.657 13.6569L12.0001 19.3137L6.34326 13.6569L7.75748 12.2427L11.0001 15.4853V1Z"
            fill="currentColor"
          />
          <path d="M18 20.2877H6V22.2877H18V20.2877Z" fill="currentColor" />
        </svg>
        <svg
          class="text-white"
          width="23"
          height="23"
          viewBox="0 0 24 24"
          fill="none"
          xmlns="http://www.w3.org/2000/svg"
        >
          <path
            fill-rule="evenodd"
            clip-rule="evenodd"
            d="M14 3V3.28988C16.8915 4.15043 19 6.82898 19 10V17H20V19H4V17H5V10C5 6.82898 7.10851 4.15043 10 3.28988V3C10 1.89543 10.8954 1 12 1C13.1046 1 14 1.89543 14 3ZM7 17H17V10C17 7.23858 14.7614 5 12 5C9.23858 5 7 7.23858 7 10V17ZM14 21V20H10V21C10 22.1046 10.8954 23 12 23C13.1046 23 14 22.1046 14 21Z"
            fill="currentColor"
          />
        </svg>
        <svg
          class="text-white"
          width="23"
          height="23"
          viewBox="0 0 24 24"
          fill="none"
          xmlns="http://www.w3.org/2000/svg"
        >
          <path
            fill-rule="evenodd"
            clip-rule="evenodd"
            d="M16 9C16 11.2091 14.2091 13 12 13C9.79086 13 8 11.2091 8 9C8 6.79086 9.79086 5 12 5C14.2091 5 16 6.79086 16 9ZM14 9C14 10.1046 13.1046 11 12 11C10.8954 11 10 10.1046 10 9C10 7.89543 10.8954 7 12 7C13.1046 7 14 7.89543 14 9Z"
            fill="currentColor"
          />
          <path
            fill-rule="evenodd"
            clip-rule="evenodd"
            d="M12 1C5.92487 1 1 5.92487 1 12C1 18.0751 5.92487 23 12 23C18.0751 23 23 18.0751 23 12C23 5.92487 18.0751 1 12 1ZM3 12C3 14.0902 3.71255 16.014 4.90798 17.5417C6.55245 15.3889 9.14627 14 12.0645 14C14.9448 14 17.5092 15.3531 19.1565 17.4583C20.313 15.9443 21 14.0524 21 12C21 7.02944 16.9706 3 12 3C7.02944 3 3 7.02944 3 12ZM12 21C9.84977 21 7.87565 20.2459 6.32767 18.9878C7.59352 17.1812 9.69106 16 12.0645 16C14.4084 16 16.4833 17.1521 17.7538 18.9209C16.1939 20.2191 14.1881 21 12 21Z"
            fill="currentColor"
          />
        </svg>
      </div>
    </nav>
    <footer
      class="fixed bottom-0 bg-neutral-950 h-[3rem] border-t border-neutral-600 w-screen md:hidden"
    >
      <div class="flex justify-between ml-2 h-10 mt-1">
        <div class="flex flex-col items-center ml-5">
          <svg
            class="text-white fill-current"
            xmlns="http://www.w3.org/2000/svg"
            enable-background="new 0 0 24 24"
            height="24"
            viewBox="0 0 24 24"
            width="24"
            focusable="false"
          >
            <g><path d="M4 21V10.08l8-6.96 8 6.96V21h-6v-6h-4v6H4z" /></g>
          </svg>
          <p class="text-white text-xs">Acceuil</p>
        </div>
        <div class="flex flex-col items-center">
          <svg
            class="text-white fill-current"
            xmlns="http://www.w3.org/2000/svg"
            height="24"
            viewBox="0 0 24 24"
            width="24"
            focusable="false"
          >
            <path
              d="M10 14.65v-5.3L15 12l-5 2.65zm7.77-4.33-1.2-.5L18 9.06c1.84-.96 2.53-3.23 1.56-5.06s-3.24-2.53-5.07-1.56L6 6.94c-1.29.68-2.07 2.04-2 3.49.07 1.42.93 2.67 2.22 3.25.03.01 1.2.5 1.2.5L6 14.93c-1.83.97-2.53 3.24-1.56 5.07.97 1.83 3.24 2.53 5.07 1.56l8.5-4.5c1.29-.68 2.06-2.04 1.99-3.49-.07-1.42-.94-2.68-2.23-3.25zm-.23 5.86-8.5 4.5c-1.34.71-3.01.2-3.72-1.14-.71-1.34-.2-3.01 1.14-3.72l2.04-1.08v-1.21l-.69-.28-1.11-.46c-.99-.41-1.65-1.35-1.7-2.41-.05-1.06.52-2.06 1.46-2.56l8.5-4.5c1.34-.71 3.01-.2 3.72 1.14.71 1.34.2 3.01-1.14 3.72L15.5 9.26v1.21l1.8.74c.99.41 1.65 1.35 1.7 2.41.05 1.06-.52 2.06-1.46 2.56z"
            />
          </svg>
          <p class="text-white text-xs">Shorts</p>
        </div>
        <div class="flex flex-col items-center">
          <svg
            class="text-white fill-current"
            xmlns="http://www.w3.org/2000/svg"
            enable-background="new 0 0 24 24"
            height="24"
            viewBox="0 0 24 24"
            width="24"
            focusable="false"
          >
            <path
              d="M10 18v-6l5 3-5 3zm7-15H7v1h10V3zm3 3H4v1h16V6zm2 3H2v12h20V9zM3 10h18v10H3V10z"
            />
          </svg>
          <p class="text-white text-xs">Abonnement</p>
        </div>
        <div class="flex flex-col items-center mr-5">
          <svg
            class="text-white fill-current"
            xmlns="http://www.w3.org/2000/svg"
            enable-background="new 0 0 24 24"
            height="24"
            viewBox="0 0 24 24"
            width="24"
            focusable="false"
          >
            <path
              d="m11 7 6 3.5-6 3.5V7zm7 13H4V6H3v15h15v-1zm3-2H6V3h15v15zM7 17h13V4H7v13z"
            />
          </svg>
          <p class="text-white text-xs">Bibliothèque</p>
        </div>
      </div>
    </footer>
    <div class="relative flex h-20">
      <div
        class="h-[40px] hidden md:flex h-screen w-[240px] flex flex-col items-start"
      >
        <button
          class="ml-5 h-9 0 w-48 mt-3 rounded-xl flex items-center gap-5 focus:bg-neutral-700 hover:bg-neutral-700"
        >
          <svg
            class="text-white fill-current"
            xmlns="http://www.w3.org/2000/svg"
            enable-background="new 0 0 24 24"
            height="24"
            viewBox="0 0 24 24"
            width="24"
            focusable="false"
          >
            <g><path d="M4 21V10.08l8-6.96 8 6.96V21h-6v-6h-4v6H4z" /></g>
          </svg>
          <p class="text-white text-sm">Acceuil</p>
        </button>
        <button
          class="ml-5 h-9 0 w-48 rounded-xl flex items-center gap-5 focus:bg-neutral-700 hover:bg-neutral-700"
        >
          <svg
            class="text-white fill-current"
            xmlns="http://www.w3.org/2000/svg"
            height="24"
            viewBox="0 0 24 24"
            width="24"
            focusable="false"
          >
            <path
              d="M10 14.65v-5.3L15 12l-5 2.65zm7.77-4.33-1.2-.5L18 9.06c1.84-.96 2.53-3.23 1.56-5.06s-3.24-2.53-5.07-1.56L6 6.94c-1.29.68-2.07 2.04-2 3.49.07 1.42.93 2.67 2.22 3.25.03.01 1.2.5 1.2.5L6 14.93c-1.83.97-2.53 3.24-1.56 5.07.97 1.83 3.24 2.53 5.07 1.56l8.5-4.5c1.29-.68 2.06-2.04 1.99-3.49-.07-1.42-.94-2.68-2.23-3.25zm-.23 5.86-8.5 4.5c-1.34.71-3.01.2-3.72-1.14-.71-1.34-.2-3.01 1.14-3.72l2.04-1.08v-1.21l-.69-.28-1.11-.46c-.99-.41-1.65-1.35-1.7-2.41-.05-1.06.52-2.06 1.46-2.56l8.5-4.5c1.34-.71 3.01-.2 3.72 1.14.71 1.34.2 3.01-1.14 3.72L15.5 9.26v1.21l1.8.74c.99.41 1.65 1.35 1.7 2.41.05 1.06-.52 2.06-1.46 2.56z"
            />
          </svg>
          <p class="text-white text-sm">Shorts</p>
        </button>
        <button
          class="ml-5 h-9 0 w-48 rounded-xl flex items-center gap-5 focus:bg-neutral-700 hover:bg-neutral-700"
        >
          <svg
            class="text-white fill-current"
            xmlns="http://www.w3.org/2000/svg"
            enable-background="new 0 0 24 24"
            height="24"
            viewBox="0 0 24 24"
            width="24"
            focusable="false"
          >
            <path
              d="M10 18v-6l5 3-5 3zm7-15H7v1h10V3zm3 3H4v1h16V6zm2 3H2v12h20V9zM3 10h18v10H3V10z"
            />
          </svg>
          <p class="text-white text-sm">Abonnement</p>
        </button>
        <div
          class="ml-[-7px] mt-1 h-2 w-[230px] flex items-center justify-center"
        >
          <div class="h-[1px] w-48 bg-neutral-600"></div>
        </div>
        <button
          class="ml-6 h-9 0 w-48 mt-3 rounded-xl flex items-center gap-5 focus:bg-neutral-700 hover:bg-neutral-700"
        >
          <svg
            class="text-white fill-current"
            xmlns="http://www.w3.org/2000/svg"
            enable-background="new 0 0 24 24"
            height="24"
            viewBox="0 0 24 24"
            width="24"
            focusable="false"
          >
            <path
              d="m11 7 6 3.5-6 3.5V7zm7 13H4V6H3v15h15v-1zm3-2H6V3h15v15zM7 17h13V4H7v13z"
            />
          </svg>
          <p class="text-white text-sm">Bibliothèque</p>
        </button>
        <button
          class="ml-6 h-9 0 w-48 rounded-xl flex items-center gap-5 focus:bg-neutral-700 hover:bg-neutral-700"
        >
          <svg
            class="text-white fill-current"
            height="24"
            viewBox="0 0 24 24"
            width="24"
            focusable="false"
          >
            <path
              d="M14.97 16.95 10 13.87V7h2v5.76l4.03 2.49-1.06 1.7zM12 3c-4.96 0-9 4.04-9 9s4.04 9 9 9 9-4.04 9-9-4.04-9-9-9m0-1c5.52 0 10 4.48 10 10s-4.48 10-10 10S2 17.52 2 12 6.48 2 12 2z"
            ></path>
          </svg>
          <p class="text-white text-sm">Historique</p>
        </button>
        <button
          class="ml-6 h-9 0 w-48 rounded-xl flex items-center gap-5 focus:bg-neutral-700 hover:bg-neutral-700"
        >
          <svg
            class="text-white fill-current"
            enable-background="new 0 0 24 24"
            height="24"
            viewBox="0 0 24 24"
            width="24"
            focusable="false"
          >
            <path d="m10 8 6 4-6 4V8zm11-5v18H3V3h18zm-1 1H4v16h16V4z"></path>
          </svg>
          <p class="text-white text-sm">Vos vidéos</p>
        </button>
        <button
          class="ml-6 h-9 0 w-48 rounded-xl flex items-center gap-5 focus:bg-neutral-700 hover:bg-neutral-700"
        >
          <svg
            class="text-white fill-current"
            height="24"
            viewBox="0 0 24 24"
            width="24"
            focusable="false"
          >
            <path
              d="M14.97 16.95 10 13.87V7h2v5.76l4.03 2.49-1.06 1.7zM12 3c-4.96 0-9 4.04-9 9s4.04 9 9 9 9-4.04 9-9-4.04-9-9-9m0-1c5.52 0 10 4.48 10 10s-4.48 10-10 10S2 17.52 2 12 6.48 2 12 2z"
            ></path>
          </svg>
          <p class="text-white text-sm">À regarder plus tard</p>
        </button>
        <button
          class="ml-6 h-9 0 w-48 rounded-xl flex items-center gap-5 focus:bg-neutral-700 hover:bg-neutral-700"
        >
          <svg
            class="text-white fill-current"
            enable-background="new 0 0 24 24"
            height="24"
            viewBox="0 0 24 24"
            width="24"
            focusable="false"
          >
            <path
              d="M18.77,11h-4.23l1.52-4.94C16.38,5.03,15.54,4,14.38,4c-0.58,0-1.14,0.24-1.52,0.65L7,11H3v10h4h1h9.43 c1.06,0,1.98-0.67,2.19-1.61l1.34-6C21.23,12.15,20.18,11,18.77,11z M7,20H4v-8h3V20z M19.98,13.17l-1.34,6 C18.54,19.65,18.03,20,17.43,20H8v-8.61l5.6-6.06C13.79,5.12,14.08,5,14.38,5c0.26,0,0.5,0.11,0.63,0.3 c0.07,0.1,0.15,0.26,0.09,0.47l-1.52,4.94L13.18,12h1.35h4.23c0.41,0,0.8,0.17,1.03,0.46C19.92,12.61,20.05,12.86,19.98,13.17z"
            ></path>
          </svg>
          <p class="text-white text-sm">Vidéos "J'aime"</p>
        </button>
        <button
          class="ml-6 h-9 0 w-48 rounded-xl flex items-center gap-5 focus:bg-neutral-700 hover:bg-neutral-700"
        >
          <svg
            class="text-white fill-current"
            height="24"
            viewBox="0 0 24 24"
            width="24"
            focusable="false"
          >
            <path
              d="M22 7H2v1h20V7zm-9 5H2v-1h11v1zm0 4H2v-1h11v1zm2 3v-8l7 4-7 4z"
            ></path>
          </svg>
          <p class="text-white text-sm">Rap</p>
        </button>
      </div>
      <div
        id="scrollContainer"
        class="select-none h-8 mt-3 ml-4 grid gap-3 grid-flow-col w-max overflow-x-hidden"
      >
        <button
          class="h-[30px] w-[50px] text-center flex justify-center min-w-[12px] text-sm flex items-center bg-white rounded-lg"
        >
          Tous
        </button>
        <button
          class="h-[30px] w-max p-2 text-center flex justify-center min-w-[12px] text-sm flex items-center bg-neutral-800 hover:bg-neutral-700 duration-300 text-white rounded-lg"
        >
          Mix
        </button>
        <button
          class="h-[30px] w-max p-2 text-center flex justify-center min-w-[12px] text-sm flex items-center bg-neutral-800 hover:bg-neutral-700 duration-300 text-white rounded-lg"
        >
          Musique
        </button>
        <button
          class="h-[30px] w-max p-2 text-center flex justify-center min-w-[12px] text-sm flex items-center bg-neutral-800 hover:bg-neutral-700 duration-300 text-white rounded-lg"
        >
          jeux Vidéos
        </button>
        <button
          class="h-[30px] w-max p-2 text-center flex justify-center min-w-[12px] text-sm flex items-center bg-neutral-800 hover:bg-neutral-700 duration-300 text-white rounded-lg"
        >
          Musique
        </button>
        <button
          class="h-[30px] w-max p-2 text-center flex justify-center min-w-[12px] text-sm flex items-center bg-neutral-800 hover:bg-neutral-700 duration-300 text-white rounded-lg"
        >
          Podcast
        </button>
        <button
          class="h-[30px] w-max p-2 text-center flex justify-center min-w-[12px] text-sm flex items-center bg-neutral-800 hover:bg-neutral-700 duration-300 text-white rounded-lg"
        >
          Amixem
        </button>
        <button
          class="h-[30px] w-max p-2 text-center flex justify-center min-w-[12px] text-sm flex items-center bg-neutral-800 hover:bg-neutral-700 duration-300 text-white rounded-lg"
        >
          RObin
        </button>
        <button
          class="h-[30px] w-max p-2 text-center flex justify-center min-w-[12px] text-sm flex items-center bg-neutral-800 hover:bg-neutral-700 duration-300 text-white rounded-lg"
        >
          matis
        </button>
        <button
          class="h-[30px] w-max p-2 text-center flex justify-center min-w-[12px] text-sm flex items-center bg-neutral-800 hover:bg-neutral-700 duration-300 text-white rounded-lg"
        >
          mig
        </button>
        <button
          class="h-[30px] w-max p-2 text-center flex justify-center min-w-[12px] text-sm flex items-center bg-neutral-800 hover:bg-neutral-700 duration-300 text-white rounded-lg"
        >
          vector
        </button>
        <button
          class="h-[30px] w-max p-2 text-center flex justify-center min-w-[12px] text-sm flex items-center bg-neutral-800 hover:bg-neutral-700 duration-300 text-white rounded-lg"
        >
          grue
        </button>
        <button
          class="h-[30px] w-max p-2 text-center flex justify-center min-w-[12px] text-sm flex items-center bg-neutral-800 hover:bg-neutral-700 duration-300 text-white rounded-lg"
        >
          je sais pas
        </button>
        <button
          class="h-[30px] w-max p-2 text-center flex justify-center min-w-[12px] text-sm flex items-center bg-neutral-800 hover:bg-neutral-700 duration-300 text-white rounded-lg"
        >
          jeux Vidéos
        </button>
        <button
          class="h-[30px] w-max p-2 text-center flex justify-center min-w-[12px] text-sm flex items-center bg-neutral-800 hover:bg-neutral-700 duration-300 text-white rounded-lg"
        >
          jeux Vidéos
        </button>
        <button
          class="h-[30px] w-max p-2 text-center flex justify-center min-w-[12px] text-sm flex items-center bg-neutral-800 hover:bg-neutral-700 duration-300 text-white rounded-lg"
        >
          jeux Vidéos
        </button>
        <button
          class="h-[30px] w-max p-2 text-center flex justify-center min-w-[12px] text-sm flex items-center bg-neutral-800 hover:bg-neutral-700 duration-300 text-white rounded-lg"
        >
          jeux Vidéos
        </button>
        <button
          class="h-[30px] w-max p-2 text-center flex justify-center min-w-[12px] text-sm flex items-center bg-neutral-800 hover:bg-neutral-700 duration-300 text-white rounded-lg"
        >
          jeux Vidéos
        </button>
        <button
          class="h-[30px] w-max p-2 text-center flex justify-center min-w-[12px] text-sm flex items-center bg-neutral-800 hover:bg-neutral-700 duration-300 text-white rounded-lg"
        >
          jeux Vidéos
        </button>
        <button
          class="h-[30px] w-max p-2 text-center flex justify-center min-w-[12px] text-sm flex items-center bg-neutral-800 hover:bg-neutral-700 duration-300 text-white rounded-lg"
        >
          jeux Vidéos
        </button>
        <button
          class="h-[30px] w-max p-2 text-center flex justify-center min-w-[12px] text-sm flex items-center bg-neutral-800 hover:bg-neutral-700 duration-300 text-white rounded-lg"
        >
          jeux Vidéos
        </button>
        <button
          class="h-[30px] w-max p-2 text-center flex justify-center min-w-[12px] text-sm flex items-center bg-neutral-800 hover:bg-neutral-700 duration-300 text-white rounded-lg"
        >
          jeux Vidéos
        </button>
        <button
          class="h-[30px] w-max p-2 text-center flex justify-center min-w-[12px] text-sm flex items-center bg-neutral-800 hover:bg-neutral-700 duration-300 text-white rounded-lg"
        >
          jeux Vidéos
        </button>
        <button
          class="h-[30px] w-max p-2 text-center flex justify-center min-w-[12px] text-sm flex items-center bg-neutral-800 hover:bg-neutral-700 duration-300 text-white rounded-lg"
        >
          jeux Vidéos
        </button>
      </div>
    </div>
  </div>
  <div class="h-screen w-[88vw] lg:ml-56">
    <div
      class="lg:grid lg:grid-cols-2 xl:grid-cols-3 2xl:grid-cols-4 gap-y-5 md:gap-y-12 flex flex-col w-screen lg:w-[88vw] items-center"
    >
      <div>
        <img
          alt=""
          class="rounded-xl h-52"
          src="https://i.ytimg.com/vi/AvslJ37tVE4/hq720.jpg?sqp=-oaymwEXCNAFEJQDSFryq4qpAwkIARUAAIhCGAE=&rs=AOn4CLDktqz0V4oHZlyy7Hl82ifiu2o47w"
        />
        <div class="flex gap-2 mt-2 ml-2 md:ml-0 ml-2 md:ml-0">
          <img
            class="rounded-full h-9 object-cover object-center"
            src="https://yt3.ggpht.com/N-7QdSSlKBfqXuk9WT1nIg88SPON1FOBUSozJqclQDFVlF6tHKBxct0eeDlEptzDvSSQGCqcnTI=s68-c-k-c0x00ffffff-no-rj"
            alt=""
          />
          <div>
            <p
              class="text-white w-64 text-md font-bold line-clamp-1 md:line-clamp-2 line-clamp-1 md:line-clamp-2"
            >
              Comment je suis devenu le pire détective de France...
            </p>
            <div class="flex gap-1 md:flex-col">
              <p class="text-neutral-400">Basti UI</p>
              <p class="md:hidden text-neutral-400">-</p>
              <p class="text-neutral-400">19 k vues - il y a 3 mois</p>
            </div>
          </div>
        </div>
        <div></div>
      </div>
      <div>
        <img
          alt=""
          class="rounded-xl h-52"
          src="https://i.ytimg.com/vi/iooCSUvLX0Q/hq720.jpg?sqp=-oaymwEXCNAFEJQDSFryq4qpAwkIARUAAIhCGAE=&rs=AOn4CLAB0XD91SroFAnIhA5ufOGm-XyoPA"
        />
        <div class="flex gap-2 mt-2 ml-2 md:ml-0">
          <img
            class="rounded-full h-9"
            src="https://yt3.ggpht.com/ytc/APkrFKZFRzpVFevZ4oX67XwPfHGV_f1m1rcGRJjMBKPfaQ=s68-c-k-c0x00ffffff-no-rj"
            alt=""
          />
          <div>
            <p
              class="text-white w-64 text-md font-bold line-clamp-1 md:line-clamp-2 line-clamp-1 md:line-clamp-2"
            >
              Comment je suis devenu le pire détective de France...
            </p>
            <div class="flex gap-1 md:flex-col">
              <p class="text-neutral-400">Basti UI</p>
              <p class="md:hidden text-neutral-400">-</p>
              <p class="text-neutral-400">19 k vues - il y a 3 mois</p>
            </div>
          </div>
        </div>
        <div></div>
      </div>
      <div>
        <img
          alt=""
          class="rounded-xl h-52"
          src="https://i.ytimg.com/vi/mu0xDfMiJQw/hq720.jpg?sqp=-oaymwEXCNAFEJQDSFryq4qpAwkIARUAAIhCGAE=&rs=AOn4CLCE_QejryYF0CZRrE7xsgypMnzpPQ"
        />
        <div class="flex gap-2 mt-2 ml-2 md:ml-0">
          <img
            class="rounded-full h-9 object-cover object-center"
            src="https://yt3.ggpht.com/ytc/APkrFKZFRzpVFevZ4oX67XwPfHGV_f1m1rcGRJjMBKPfaQ=s68-c-k-c0x00ffffff-no-rj"
            alt=""
          />
          <div>
            <p
              class="text-white w-64 text-md font-bold line-clamp-1 md:line-clamp-2 line-clamp-1 md:line-clamp-2"
            >
              Comment je suis devenu le pire détective de France...
            </p>
            <div class="flex gap-1 md:flex-col">
              <p class="text-neutral-400">Basti UI</p>
              <p class="md:hidden text-neutral-400">-</p>
              <p class="text-neutral-400">19 k vues - il y a 3 mois</p>
            </div>
          </div>
        </div>
        <div></div>
      </div>
      <div>
        <img
          alt=""
          class="rounded-xl h-52"
          src="https://i.ytimg.com/vi/ZI3rdGB1JxU/hq720.jpg?sqp=-oaymwEXCNAFEJQDSFryq4qpAwkIARUAAIhCGAE=&rs=AOn4CLAELRRkwndRaDB1jNIl5hLlFZAJfg"
        />
        <div class="flex gap-2 mt-2 ml-2 md:ml-0">
          <img
            class="rounded-full h-9 object-cover object-center"
            src="https://yt3.ggpht.com/ytc/APkrFKZFRzpVFevZ4oX67XwPfHGV_f1m1rcGRJjMBKPfaQ=s68-c-k-c0x00ffffff-no-rj"
            alt=""
          />
          <div>
            <p
              class="text-white w-64 text-md font-bold line-clamp-1 md:line-clamp-2 line-clamp-1 md:line-clamp-2"
            >
              Comment je suis devenu le pire détective de France...
            </p>
            <div class="flex gap-1 md:flex-col">
              <p class="text-neutral-400">Basti UI</p>
              <p class="md:hidden text-neutral-400">-</p>
              <p class="text-neutral-400">19 k vues - il y a 3 mois</p>
            </div>
          </div>
        </div>
        <div></div>
      </div>
      <div>
        <img
          alt=""
          class="rounded-xl h-52"
          src="https://i.ytimg.com/vi/EuKkxzKit7I/hq720.jpg?sqp=-oaymwEXCNAFEJQDSFryq4qpAwkIARUAAIhCGAE=&amp;rs=AOn4CLC_GQUFSsju-VqrpYdSIZfFZXHuJA"
        />
        <div class="flex gap-2 mt-2 ml-2 md:ml-0">
          <img
            class="rounded-full h-9 object-cover object-center"
            src="https://yt3.ggpht.com/ytc/APkrFKZFRzpVFevZ4oX67XwPfHGV_f1m1rcGRJjMBKPfaQ=s68-c-k-c0x00ffffff-no-rj"
            alt=""
          />
          <div>
            <p
              class="text-white w-64 text-md font-bold line-clamp-1 md:line-clamp-2 line-clamp-1 md:line-clamp-2"
            >
              Comment je suis devenu le pire détective de France...
            </p>
            <div class="flex gap-1 md:flex-col">
              <p class="text-neutral-400">Basti UI</p>
              <p class="md:hidden text-neutral-400">-</p>
              <p class="text-neutral-400">19 k vues - il y a 3 mois</p>
            </div>
          </div>
        </div>
        <div></div>
      </div>
      <div>
        <img
          alt=""
          class="rounded-xl h-52"
          src="https://i.ytimg.com/vi/5O24gWP279w/hq720.jpg?sqp=-oaymwEXCNAFEJQDSFryq4qpAwkIARUAAIhCGAE=&rs=AOn4CLBuhtcWR61Ug_QUDcAjEQZWZs54kA"
        />
        <div class="flex gap-2 mt-2 ml-2 md:ml-0">
          <img
            class="rounded-full h-9 object-cover object-center"
            src="https://yt3.ggpht.com/ytc/APkrFKZFRzpVFevZ4oX67XwPfHGV_f1m1rcGRJjMBKPfaQ=s68-c-k-c0x00ffffff-no-rj"
            alt=""
          />
          <div>
            <p
              class="text-white w-64 text-md font-bold line-clamp-1 md:line-clamp-2 line-clamp-1 md:line-clamp-2"
            >
              Comment je suis devenu le pire détective de France...
            </p>
            <div class="flex gap-1 md:flex-col">
              <p class="text-neutral-400">Basti UI</p>
              <p class="md:hidden text-neutral-400">-</p>
              <p class="text-neutral-400">19 k vues - il y a 3 mois</p>
            </div>
          </div>
        </div>
        <div></div>
      </div>
      <div>
        <img
          alt=""
          class="rounded-xl h-52"
          src="https://i.ytimg.com/vi/OfbQQEiF80Q/hq720.jpg?sqp=-oaymwEXCNAFEJQDSFryq4qpAwkIARUAAIhCGAE=&rs=AOn4CLD5K9SVoegogNSSZEyvsrzH-Lgc9Q"
        />
        <div class="flex gap-2 mt-2 ml-2 md:ml-0">
          <img
            class="rounded-full h-9 object-cover object-center"
            src="https://yt3.ggpht.com/ytc/APkrFKZFRzpVFevZ4oX67XwPfHGV_f1m1rcGRJjMBKPfaQ=s68-c-k-c0x00ffffff-no-rj"
            alt=""
          />
          <div>
            <p
              class="text-white w-64 text-md font-bold line-clamp-1 md:line-clamp-2 line-clamp-1 md:line-clamp-2"
            >
              Comment je suis devenu le pire détective de France...
            </p>
            <div class="flex gap-1 md:flex-col">
              <p class="text-neutral-400">Basti UI</p>
              <p class="md:hidden text-neutral-400">-</p>
              <p class="text-neutral-400">19 k vues - il y a 3 mois</p>
            </div>
          </div>
        </div>
        <div></div>
      </div>
      <div>
        <img
          alt=""
          class="rounded-xl h-52"
          src="https://i.ytimg.com/vi/G-g5LVLHaEM/hq720.jpg?sqp=-oaymwEXCNAFEJQDSFryq4qpAwkIARUAAIhCGAE=&rs=AOn4CLCazG6Vl9TYentIRd10ICiGTLxRHg"
        />
        <div class="flex gap-2 mt-2 ml-2 md:ml-0">
          <img
            class="rounded-full h-9 object-cover object-center"
            src="https://yt3.ggpht.com/ytc/APkrFKZFRzpVFevZ4oX67XwPfHGV_f1m1rcGRJjMBKPfaQ=s68-c-k-c0x00ffffff-no-rj"
            alt=""
          />
          <div>
            <p
              class="text-white w-64 text-md font-bold line-clamp-1 md:line-clamp-2 line-clamp-1 md:line-clamp-2"
            >
              Comment je suis devenu le pire détective de France...
            </p>
            <div class="flex gap-1 md:flex-col">
              <p class="text-neutral-400">Basti UI</p>
              <p class="md:hidden text-neutral-400">-</p>
              <p class="text-neutral-400">19 k vues - il y a 3 mois</p>
            </div>
          </div>
        </div>
        <div></div>
      </div>
      <div>
        <img
          alt=""
          class="rounded-xl h-52"
          src="https://i.ytimg.com/vi/njXLcyrMMKc/hq720.jpg?sqp=-oaymwEXCNAFEJQDSFryq4qpAwkIARUAAIhCGAE=&rs=AOn4CLAhDdFq3S4VED49E3aB_HJSEWDA8g"
        />
        <div class="flex gap-2 mt-2 ml-2 md:ml-0">
          <img
            class="rounded-full h-9 object-cover object-center"
            src="https://yt3.ggpht.com/ytc/APkrFKZFRzpVFevZ4oX67XwPfHGV_f1m1rcGRJjMBKPfaQ=s68-c-k-c0x00ffffff-no-rj"
            alt=""
          />
          <div>
            <p
              class="text-white w-64 text-md font-bold line-clamp-1 md:line-clamp-2 line-clamp-1 md:line-clamp-2"
            >
              Comment je suis devenu le pire détective de France...
            </p>
            <div class="flex gap-1 md:flex-col">
              <p class="text-neutral-400">Basti UI</p>
              <p class="md:hidden text-neutral-400">-</p>
              <p class="text-neutral-400">19 k vues - il y a 3 mois</p>
            </div>
          </div>
        </div>
        <div></div>
      </div>
      <div>
        <img
          alt=""
          class="rounded-xl h-52"
          src="https://i.ytimg.com/vi/rRkT4tMXNQY/hq720.jpg?sqp=-oaymwEXCNAFEJQDSFryq4qpAwkIARUAAIhCGAE=&rs=AOn4CLAJe7IouaKzXNEKyJCqjXzzAab8gQ"
        />
        <div class="flex gap-2 mt-2 ml-2 md:ml-0">
          <img
            class="rounded-full h-9 object-cover object-center"
            src="https://yt3.ggpht.com/ytc/APkrFKZFRzpVFevZ4oX67XwPfHGV_f1m1rcGRJjMBKPfaQ=s68-c-k-c0x00ffffff-no-rj"
            alt=""
          />
          <div>
            <p
              class="text-white w-64 text-md font-bold line-clamp-1 md:line-clamp-2 line-clamp-1 md:line-clamp-2"
            >
              Comment je suis devenu le pire détective de France...
            </p>
            <div class="flex gap-1 md:flex-col">
              <p class="text-neutral-400">Basti UI</p>
              <p class="md:hidden text-neutral-400">-</p>
              <p class="text-neutral-400">19 k vues - il y a 3 mois</p>
            </div>
          </div>
        </div>
        <div></div>
      </div>
      <div>
        <img
          alt=""
          class="rounded-xl h-52"
          src="https://i.ytimg.com/vi/EuKkxzKit7I/hq720.jpg?sqp=-oaymwEXCNAFEJQDSFryq4qpAwkIARUAAIhCGAE=&amp;rs=AOn4CLC_GQUFSsju-VqrpYdSIZfFZXHuJA"
        />
        <div class="flex gap-2 mt-2 ml-2 md:ml-0">
          <img
            class="rounded-full h-9 object-cover object-center"
            src="https://yt3.ggpht.com/ytc/APkrFKZFRzpVFevZ4oX67XwPfHGV_f1m1rcGRJjMBKPfaQ=s68-c-k-c0x00ffffff-no-rj"
            alt=""
          />
          <div>
            <p
              class="text-white w-64 text-md font-bold line-clamp-1 md:line-clamp-2 line-clamp-1 md:line-clamp-2"
            >
              Comment je suis devenu le pire détective de France...
            </p>
            <div class="flex gap-1 md:flex-col">
              <p class="text-neutral-400">Basti UI</p>
              <p class="md:hidden text-neutral-400">-</p>
              <p class="text-neutral-400">19 k vues - il y a 3 mois</p>
            </div>
          </div>
        </div>
        <div></div>
      </div>
      <div>
        <img
          alt=""
          class="rounded-xl h-52"
          src="https://i.ytimg.com/vi/EuKkxzKit7I/hq720.jpg?sqp=-oaymwEXCNAFEJQDSFryq4qpAwkIARUAAIhCGAE=&amp;rs=AOn4CLC_GQUFSsju-VqrpYdSIZfFZXHuJA"
        />
        <div class="flex gap-2 mt-2 ml-2 md:ml-0">
          <img
            class="rounded-full h-9 object-cover object-center"
            src="https://yt3.ggpht.com/ytc/APkrFKZFRzpVFevZ4oX67XwPfHGV_f1m1rcGRJjMBKPfaQ=s68-c-k-c0x00ffffff-no-rj"
            alt=""
          />
          <div>
            <p
              class="text-white w-64 text-md font-bold line-clamp-1 md:line-clamp-2 line-clamp-1 md:line-clamp-2"
            >
              Comment je suis devenu le pire détective de France...
            </p>
            <div class="flex gap-1 md:flex-col">
              <p class="text-neutral-400">Basti UI</p>
              <p class="md:hidden text-neutral-400">-</p>
              <p class="text-neutral-400">19 k vues - il y a 3 mois</p>
            </div>
          </div>
        </div>
        <div></div>
      </div>
    </div>
    <div class="h-6 w-6"></div>
  </div>
</template>

<style>
body {
  overflow-x: hidden;
  background-color: rgb(10, 10, 10);
}
</style>
