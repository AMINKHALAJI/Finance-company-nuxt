<template>
  <div class="w-full py-20 px-4 bg-white">
    <div class="max-w-6xl mx-auto">
      <h1 class="text-3xl text-green-600 font-bold text-center py-8">
        Welcome to Our Projects
      </h1>
      <div class="w-full py-20 px-4 mx-auto text-green-400 my-4 bg-black">
        <div
          class="flex flex-col sm:flex-row items-center justify-between w-full"
        >
          <input
            v-model="searchTerm"
            class="p-3 flex w-full rounded-md text-black"
            
            type="text"
            placeholder="Search for projects"
          /><button
            @click="filteredProjects"
            class="bg-[#00df9a] text-black rounded-md font-medium w-48 ml-4 my-6 px-6 py-3"
          >
            Search
          </button>
        </div>
      </div>
    </div>

    <div v-if="!searchTerm" class="max-w-6xl mx-auto grid md:grid-cols-3 gap-8">
      <div 
        v-for="project in projects"
        :key="project.id"
        class="w-full shadow-xl flex flex-col p-4 my-4 rounded-lg hover:scale-105 duration-300"
      >
        <h2 class="text-3xl font-bold text-center py-8">{{ project.title }}</h2>
        <p class="text-left text-xl font-sans">{{ project.description }}</p>
      </div>
    </div>

    <div v-else class="max-w-6xl mx-auto grid md:grid-cols-3 gap-8">
      <div 
        v-for="project in filteredProjects" 
        :key="project.id"
        class="w-full shadow-xl flex flex-col p-4 my-4 rounded-lg hover:scale-105 duration-300"
      >
        <h2 class="text-3xl font-bold text-center py-8">{{ project.title }}</h2>
        <p class="text-left text-xl font-sans">{{ project.description }}</p>
      </div>
    </div>

  </div>
</template>

<script setup>

// const { data: projects } = await useFetch(
//   "https://jsonplaceholder.typicode.com/posts?_limit=20"
// );
// const projectsVal = projects.value;
// console.log(projects);

const projects = [
  {
    id: 1,
    title: "Investment Portfolio Optimization",
    description:
      "Implement a sophisticated algorithm for optimizing investment portfolios, maximizing returns while managing risk.",
    imageUrl: "https://via.placeholder.com/300x200?text=Project1",
  },
  {
    id: 2,
    title: "Financial Education Program",
    description:
      "Launch an educational initiative to improve financial literacy in the community. Conduct workshops and seminars on budgeting, saving, and investing.",
    imageUrl: "https://via.placeholder.com/300x200?text=Project2",
  },
  {
    id: 3,
    title: "Cryptocurrency Trading Platform",
    description:
      "Develop a secure and user-friendly platform for cryptocurrency trading. Implement advanced features for real-time market analysis and trading strategies.",
    imageUrl: "https://via.placeholder.com/300x200?text=Project3",
  },
  {
    id: 4,
    title: "Estate Planning Services",
    description:
      "Provide comprehensive estate planning services, including wills, trusts, and inheritance planning, to ensure clients' assets are managed according to their wishes.",
    imageUrl: "https://via.placeholder.com/300x200?text=Project4",
  },
  {
    id: 5,
    title: "Startup Funding Consultation",
    description:
      "Assist startup companies in securing funding through strategic financial planning and investor presentations. Successfully raise capital for multiple ventures.",
    imageUrl: "https://via.placeholder.com/300x200?text=Project5",
  },
  {
    id: 6,
    title: "Personal Budgeting App",
    description:
      "Develop a mobile app to help individuals manage their personal finances, track expenses, set budget goals, and receive financial insights.",
    imageUrl: "https://via.placeholder.com/300x200?text=Project6",
  },
  {
    id: 7,
    title: "Real Estate Investment Analysis",
    description:
      "Build a tool for real estate investors to analyze potential investment properties, considering factors such as ROI, cash flow, and market trends.",
    imageUrl: "https://via.placeholder.com/300x200?text=Project7",
  },
  {
    id: 8,
    title: "Credit Score Improvement Program",
    description:
      "Create a program to help individuals improve their credit scores through personalized advice, credit monitoring, and financial education.",
    imageUrl: "https://via.placeholder.com/300x200?text=Project8",
  },
  {
    id: 9,
    title: "Retirement Planning Services",
    description:
      "Offer retirement planning services to individuals and businesses, providing guidance on savings, investments, and pension options for a secure retirement.",
    imageUrl: "https://via.placeholder.com/300x200?text=Project9",
  },
  {
    id: 10,
    title: "Sustainable Investment Fund",
    description:
      "Establish a fund focused on sustainable and socially responsible investments. Support environmentally friendly projects and companies with a positive impact.",
    imageUrl: "https://via.placeholder.com/300x200?text=Project10",
  },
  {
    id: 11,
    title: "Small Business Financing Solutions",
    description:
      "Create a platform offering financing solutions tailored to small businesses, including loans, lines of credit, and financial advisory services.",
    imageUrl: "https://via.placeholder.com/300x200?text=Project11",
  },
  {
    id: 12,
    title: "Tax Planning Software",
    description:
      "Develop software that simplifies tax planning for individuals and businesses, ensuring compliance with tax laws and maximizing available deductions.",
    imageUrl: "https://via.placeholder.com/300x200?text=Project12",
  },
  {
    id: 13,
    title: "Healthcare Investment Opportunities",
    description:
      "Explore investment opportunities in the healthcare sector, focusing on innovative startups, medical technologies, and pharmaceutical developments.",
    imageUrl: "https://via.placeholder.com/300x200?text=Project13",
  },
  {
    id: 14,
    title: "Debt Consolidation Services",
    description:
      "Offer services to help individuals consolidate and manage their debts, providing a clear path to debt repayment and financial stability.",
    imageUrl: "https://via.placeholder.com/300x200?text=Project14",
  },
  {
    id: 15,
    title: "Educational Investment Fund",
    description:
      "Create an investment fund to support educational initiatives, scholarships, and projects that contribute to the advancement of education globally.",
    imageUrl: "https://via.placeholder.com/300x200?text=Project15",
  },
  {
    id: 16,
    title: "Automated Investment Advisory",
    description:
      "Develop an AI-driven investment advisory platform that analyzes market trends, assesses risk profiles, and recommends personalized investment strategies.",
    imageUrl: "https://via.placeholder.com/300x200?text=Project16",
  },
  {
    id: 17,
    title: "Charitable Giving Platform",
    description:
      "Build a platform that facilitates charitable giving, allowing users to contribute to causes they care about and track the impact of their donations.",
    imageUrl: "https://via.placeholder.com/300x200?text=Project17",
  },
  {
    id: 18,
    title: "Peer-to-Peer Lending Marketplace",
    description:
      "Create a marketplace connecting borrowers with individual lenders, offering competitive interest rates and streamlined lending processes.",
    imageUrl: "https://via.placeholder.com/300x200?text=Project18",
  },
];

const searchTerm = ref("");

const originalProjects = ref(projects).value;

const filteredProjects = computed (() => {

  return(originalProjects.filter((project) => {
    // Customize the conditions based on your search criteria
    return(
      project.title.toLowerCase().includes(searchTerm.value.toLowerCase()) ||
      project.description.toLowerCase().includes(searchTerm.value.toLowerCase())
    );
    
  })); 
});


</script>
