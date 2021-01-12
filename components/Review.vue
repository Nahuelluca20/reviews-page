<template>
  <div class="my-8 md:my-1">
    <div class="border border-gray6-500 p-3 rounded-md">
      <img v-if="rating === 3" src="../static/images/3stars.svg" alt="" />
      <img
        v-else-if="rating === 5"
        src="../static/images/5stars.svg"
        alt=""
        class="mb-2"
      />
      <img v-else src="../static/images/4stars.svg" alt="" class="mb-2" />
      <small class="text-gray6 text-xs">
        {{ author }}
        {{
          new Date(date).toLocaleString(es - Es, {
            weekday: 'long',
            year: 'numeric',
            month: 'long',
            day: 'numeric',
            hour12: 'false',
          })
        }}
      </small>
      <p class="text-dark3 text-base font-medium mt-2">
        {{ comment }}
      </p>
      <div class="flex my-3 items-center">
        <button
          class="group focus:outline-none py-2 outline-none px-4 border border-gray3-500 text-dark6 text-sm rounded-md flex items-center focus:bg-green3 focus:text-white"
        >
          <svg
            class="mr-1 fill-current text-dark6 group-focus:text-white"
            width="16"
            height="16"
            viewBox="0 0 16 16"
            xmlns="http://www.w3.org/2000/svg"
          >
            <mask
              id="mask0"
              mask-type="alpha"
              maskUnits="userSpaceOnUse"
              x="0"
              y="0"
              width="16"
              height="16"
            >
              <g clip-path="url(#clip0)">
                <path
                  d="M1.33333 13.3333H2.66667C3.03333 13.3333 3.33333 13.0333 3.33333 12.6667V6.66668C3.33333 6.30001 3.03333 6.00001 2.66667 6.00001H1.33333V13.3333ZM14.5533 8.58668C14.6267 8.42001 14.6667 8.24001 14.6667 8.05334V7.33334C14.6667 6.60001 14.0667 6.00001 13.3333 6.00001H9.66667L10.28 2.90001C10.3133 2.75334 10.2933 2.59334 10.2267 2.46001C10.0733 2.16001 9.88 1.88668 9.64 1.64668L9.33333 1.33334L5.06 5.60668C4.80667 5.86001 4.66667 6.20001 4.66667 6.55334V11.78C4.66667 12.6333 5.36667 13.3333 6.22667 13.3333H11.6333C12.1 13.3333 12.54 13.0867 12.78 12.6867L14.5533 8.58668Z"
                />
              </g>
            </mask>
            <g mask="url(#mask0)">
              <rect width="16" height="16" />
            </g>
            <defs>
              <clipPath id="clip0">
                <rect width="16" height="16" />
              </clipPath>
            </defs>
          </svg>
          Es útil
        </button>
        <small class="ml-3 p-0 text-gray6 text-sm">
          {{ useful_count }} personas creéis que es útil
        </small>
      </div>
    </div>
  </div>
</template>

<script>
import axios from 'axios'
export default {
  name: 'Review',
  props: ['author', 'date', 'comment', 'useful_count', 'rating'],
}
</script>
