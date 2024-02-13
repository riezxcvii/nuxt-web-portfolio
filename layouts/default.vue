<template>
    <!-- animated background template -->
    <div>
        <ul class="background z-10 h-full">
            <li></li>
            <li></li>
            <li></li>
            <li></li>
            <li></li>
            <li></li>
            <li></li>
            <li></li>
            <li></li>
            <li></li>
            <li></li>
            <li></li>
            <li></li>
            <li></li>
            <li></li>
        </ul>
    </div>

    <div class="sticky top-0">
        <NavBar />
    </div>
    <div>
        <!-- output pages/components here -->
        <slot></slot>
    </div>
</template>