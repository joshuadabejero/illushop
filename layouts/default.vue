<template>
  <div>
    <NavigationBar
      :brand="'Illushop'"
      :links="[
        { name: 'Dashboard', href: '/dashboard' },
        { name: 'Profile', href: '/profile' },
        { name: 'Settings', href: '/settings' },
      ]"
    />
    <slot />
  </div>
</template>
