<template>
    <div class="h-16 bg-gray-100">
        <nav class="bg-white border-b border-gray-100">
            <!-- Primary Navigation Menu -->
            <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
                <div class="flex justify-between h-16">
                    <div class="flex">                       

                        <!-- Responsive Navigation Menu for harburger -->
                        <div :class="{'block absolute left-0 top-16': showingNavigationSidebar, 'hidden': ! showingNavigationSidebar}" class="md:hidden">
                            <div class="-md:ml-5 max-h-full">
                                <Sidebar class="" />
                            </div>
                        </div>

                        <!-- Hamburger for sidebar on mobile -->
                        <div class="mr-2 flex items-center md:hidden">
                            <button @click="showingNavigationSidebar = ! showingNavigationSidebar" class="inline-flex items-center justify-center p-2 rounded-md text-gray-400 hover:text-gray-500 hover:bg-gray-100 focus:outline-none focus:bg-gray-100 focus:text-gray-500 transition duration-150 ease-in-out">
                                <svg class="h-6 w-6" stroke="currentColor" fill="none" viewBox="0 0 24 24">
                                    <path :class="{'hidden': showingNavigationSidebar, 'inline-flex': ! showingNavigationSidebar }" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16" />
                                    <path :class="{'hidden': ! showingNavigationSidebar, 'inline-flex': showingNavigationSidebar }" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12" />
                                </svg>
                            </button>
                        </div>

                        <!-- Navigation Links -->
                        <div class="hidden space-x-8 sm:-my-px sm:ml-10 sm:flex">
                            <breeze-nav-link :href="route('dashboard')" :active="route().current('dashboard')">
                                Dashboard
                            </breeze-nav-link>
                        </div>
                    </div> 
                </div>
            </div>

            <!-- Responsive Navigation Menu for harburger -->
            <div :class="{'block': showingNavigationDropdown, 'hidden': ! showingNavigationDropdown}" class="sm:hidden">
                <div class="pt-2 pb-3 space-y-1">
                    <breeze-responsive-nav-link :href="route('dashboard')" :active="route().current('dashboard')">
                        Dashboard
                    </breeze-responsive-nav-link>
                </div>

                <!-- Responsive Settings Options -->
                <div class="pt-4 pb-1 border-t border-gray-200">
                    <div class="flex items-center px-4">
                        <div class="font-medium text-base text-gray-800">page prop auth </div>
                        <div class="font-medium text-sm text-gray-500">user email </div>
                    </div>

                    <div class="mt-3 space-y-1">
                        <breeze-responsive-nav-link :href="route('logout')" method="post" as="button">
                            Log Out
                        </breeze-responsive-nav-link>
                    </div>
                </div>
            </div>
        </nav>

    </div>
</template>


<script>
    import BreezeApplicationLogo from '@/Components/ApplicationLogo'
    import BreezeDropdown from '@/Components/Dropdown'
    import BreezeDropdownLink from '@/Components/DropdownLink'
    import BreezeNavLink from '@/Components/NavLink'
    import BreezeResponsiveNavLink from '@/Components/ResponsiveNavLink'
    import Sidebar from '@/Components/Sidebar'

    export default {
        components: {
            BreezeApplicationLogo,
            BreezeDropdown,
            BreezeDropdownLink,
            BreezeNavLink,
            BreezeResponsiveNavLink,
            Sidebar
        },

        data() {
            return {
                showingNavigationDropdown: false,
                showingNavigationSidebar: false,
            }
        },
    }
</script>
