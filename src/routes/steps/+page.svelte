<div class="m-4">
    <nav aria-label="Progress">
      <ol role="list" class="space-y-4 md:flex md:space-x-8 md:space-y-0">
        <li class="md:flex-1">
          <!-- Completed Step -->
          <a href="#" class="group flex flex-col border-l-4 border-indigo-600 py-2 pl-4 hover:border-indigo-800 md:border-l-0 md:border-t-4 md:pb-0 md:pl-0 md:pt-4">
            <span class="text-sm font-medium text-indigo-600 group-hover:text-indigo-800">Step 1</span>
            <span class="text-sm font-medium">Job details</span>
          </a>
        </li>
        <li class="md:flex-1">
          <!-- Current Step -->
          <a href="#" class="flex flex-col border-l-4 border-indigo-600 py-2 pl-4 md:border-l-0 md:border-t-4 md:pb-0 md:pl-0 md:pt-4" aria-current="step">
            <span class="text-sm font-medium text-indigo-600">Step 2</span>
            <span class="text-sm font-medium">Application form</span>
          </a>
        </li>
        <li class="md:flex-1">
          <!-- Upcoming Step -->
          <a href="#" class="group flex flex-col border-l-4 border-gray-200 py-2 pl-4 hover:border-gray-300 md:border-l-0 md:border-t-4 md:pb-0 md:pl-0 md:pt-4">
            <span class="text-sm font-medium text-gray-500 group-hover:text-gray-700">Step 3</span>
            <span class="text-sm font-medium">Preview</span>
          </a>
        </li>
      </ol>
    </nav>
</div>

<hr class="m-4" />

<nav aria-label="Progress">
  <ol role="list" class="divide-y divide-gray-300 rounded-md border border-gray-300 md:flex md:divide-y-0">
    <li class="relative md:flex md:flex-1">
      <!-- Completed Step -->
      <a href="#" class="group flex w-full items-center">
        <span class="flex items-center px-6 py-4 text-sm font-medium">
          <span class="flex h-10 w-10 flex-shrink-0 items-center justify-center rounded-full bg-indigo-600 group-hover:bg-indigo-800">
            <svg class="h-6 w-6 text-white" viewBox="0 0 24 24" fill="currentColor" aria-hidden="true">
              <path fill-rule="evenodd" d="M19.916 4.626a.75.75 0 01.208 1.04l-9 13.5a.75.75 0 01-1.154.114l-6-6a.75.75 0 011.06-1.06l5.353 5.353 8.493-12.739a.75.75 0 011.04-.208z" clip-rule="evenodd" />
            </svg>
          </span>
          <span class="ml-4 text-sm font-medium text-gray-900">Job details</span>
        </span>
      </a>
      <!-- Arrow separator for lg screens and up -->
      <div class="absolute right-0 top-0 hidden h-full w-5 md:block" aria-hidden="true">
        <svg class="h-full w-full text-gray-300" viewBox="0 0 22 80" fill="none" preserveAspectRatio="none">
          <path d="M0 -2L20 40L0 82" vector-effect="non-scaling-stroke" stroke="currentcolor" stroke-linejoin="round" />
        </svg>
      </div>
    </li>
    <li class="relative md:flex md:flex-1">
      <!-- Current Step -->
      <a href="#" class="flex items-center px-6 py-4 text-sm font-medium" aria-current="step">
        <span class="flex h-10 w-10 flex-shrink-0 items-center justify-center rounded-full border-2 border-indigo-600">
          <span class="text-indigo-600">02</span>
        </span>
        <span class="ml-4 text-sm font-medium text-indigo-600">Application form</span>
      </a>
      <!-- Arrow separator for lg screens and up -->
      <div class="absolute right-0 top-0 hidden h-full w-5 md:block" aria-hidden="true">
        <svg class="h-full w-full text-gray-300" viewBox="0 0 22 80" fill="none" preserveAspectRatio="none">
          <path d="M0 -2L20 40L0 82" vector-effect="non-scaling-stroke" stroke="currentcolor" stroke-linejoin="round" />
        </svg>
      </div>
    </li>
    <li class="relative md:flex md:flex-1">
      <!-- Upcoming Step -->
      <a href="#" class="group flex items-center">
        <span class="flex items-center px-6 py-4 text-sm font-medium">
          <span class="flex h-10 w-10 flex-shrink-0 items-center justify-center rounded-full border-2 border-gray-300 group-hover:border-gray-400">
            <span class="text-gray-500 group-hover:text-gray-900">03</span>
          </span>
          <span class="ml-4 text-sm font-medium text-gray-500 group-hover:text-gray-900">Preview</span>
        </span>
      </a>
    </li>
  </ol>
</nav>

<hr class="m-4" />

<nav class="flex items-center justify-center" aria-label="Progress">
  <p class="text-sm font-medium">Step 2 of 4</p>
  <ol role="list" class="ml-8 flex items-center space-x-5">
    <li>
      <!-- Completed Step -->
      <a href="#" class="block h-2.5 w-2.5 rounded-full bg-indigo-600 hover:bg-indigo-900">
        <span class="sr-only">Step 1</span>
      </a>
    </li>
    <li>
      <!-- Current Step -->
      <a href="#" class="relative flex items-center justify-center" aria-current="step">
        <span class="absolute flex h-5 w-5 p-px" aria-hidden="true">
          <span class="h-full w-full rounded-full bg-indigo-200"></span>
        </span>
        <span class="relative block h-2.5 w-2.5 rounded-full bg-indigo-600" aria-hidden="true"></span>
        <span class="sr-only">Step 2</span>
      </a>
    </li>
    <li>
      <!-- Upcoming Step -->
      <a href="#" class="block h-2.5 w-2.5 rounded-full bg-gray-200 hover:bg-gray-400">
        <span class="sr-only">Step 3</span>
      </a>
    </li>
    <li>
      <!-- Upcoming Step -->
      <a href="#" class="block h-2.5 w-2.5 rounded-full bg-gray-200 hover:bg-gray-400">
        <span class="sr-only">Step 4</span>
      </a>
    </li>
  </ol>
</nav>

<hr class="m-4" />

<nav aria-label="Progress">
  <ol role="list" class="flex items-center">
    <li class="relative pr-8 sm:pr-20">
      <!-- Completed Step -->
      <div class="absolute inset-0 flex items-center" aria-hidden="true">
        <div class="h-0.5 w-full bg-indigo-600"></div>
      </div>
      <a href="#" class="relative flex h-8 w-8 items-center justify-center rounded-full bg-indigo-600 hover:bg-indigo-900">
        <svg class="h-5 w-5 text-white" viewBox="0 0 20 20" fill="currentColor" aria-hidden="true">
          <path fill-rule="evenodd" d="M16.704 4.153a.75.75 0 01.143 1.052l-8 10.5a.75.75 0 01-1.127.075l-4.5-4.5a.75.75 0 011.06-1.06l3.894 3.893 7.48-9.817a.75.75 0 011.05-.143z" clip-rule="evenodd" />
        </svg>
        <span class="sr-only">Step 1</span>
      </a>
    </li>
    <li class="relative pr-8 sm:pr-20">
      <!-- Completed Step -->
      <div class="absolute inset-0 flex items-center" aria-hidden="true">
        <div class="h-0.5 w-full bg-indigo-600"></div>
      </div>
      <a href="#" class="relative flex h-8 w-8 items-center justify-center rounded-full bg-indigo-600 hover:bg-indigo-900">
        <svg class="h-5 w-5 text-white" viewBox="0 0 20 20" fill="currentColor" aria-hidden="true">
          <path fill-rule="evenodd" d="M16.704 4.153a.75.75 0 01.143 1.052l-8 10.5a.75.75 0 01-1.127.075l-4.5-4.5a.75.75 0 011.06-1.06l3.894 3.893 7.48-9.817a.75.75 0 011.05-.143z" clip-rule="evenodd" />
        </svg>
        <span class="sr-only">Step 2</span>
      </a>
    </li>
    <li class="relative pr-8 sm:pr-20">
      <!-- Current Step -->
      <div class="absolute inset-0 flex items-center" aria-hidden="true">
        <div class="h-0.5 w-full bg-gray-200"></div>
      </div>
      <a href="#" class="relative flex h-8 w-8 items-center justify-center rounded-full border-2 border-indigo-600 bg-white" aria-current="step">
        <span class="h-2.5 w-2.5 rounded-full bg-indigo-600" aria-hidden="true"></span>
        <span class="sr-only">Step 3</span>
      </a>
    </li>
    <li class="relative pr-8 sm:pr-20">
      <!-- Upcoming Step -->
      <div class="absolute inset-0 flex items-center" aria-hidden="true">
        <div class="h-0.5 w-full bg-gray-200"></div>
      </div>
      <a href="#" class="group relative flex h-8 w-8 items-center justify-center rounded-full border-2 border-gray-300 bg-white hover:border-gray-400">
        <span class="h-2.5 w-2.5 rounded-full bg-transparent group-hover:bg-gray-300" aria-hidden="true"></span>
        <span class="sr-only">Step 4</span>
      </a>
    </li>
    <li class="relative">
      <!-- Upcoming Step -->
      <div class="absolute inset-0 flex items-center" aria-hidden="true">
        <div class="h-0.5 w-full bg-gray-200"></div>
      </div>
      <a href="#" class="group relative flex h-8 w-8 items-center justify-center rounded-full border-2 border-gray-300 bg-white hover:border-gray-400">
        <span class="h-2.5 w-2.5 rounded-full bg-transparent group-hover:bg-gray-300" aria-hidden="true"></span>
        <span class="sr-only">Step 5</span>
      </a>
    </li>
  </ol>
</nav>

<hr class="m-4" />

<div>
  <h4 class="sr-only">Status</h4>
  <p class="text-sm font-medium text-gray-900">Migrating MySQL database...</p>
  <div class="mt-6" aria-hidden="true">
    <div class="overflow-hidden rounded-full bg-gray-200">
      <div class="h-2 rounded-full bg-indigo-600" style="width: 37.5%"></div>
    </div>
    <div class="mt-6 hidden grid-cols-4 text-sm font-medium text-gray-600 sm:grid">
      <div class="text-indigo-600">Copying files</div>
      <div class="text-center text-indigo-600">Migrating database</div>
      <div class="text-center">Compiling assets</div>
      <div class="text-right">Deployed</div>
    </div>
  </div>
</div>

