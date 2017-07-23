<template>
  <div>
      <q-layout>
        <!-- Header -->
        <div slot="header" class="toolbar">
            <!-- opens left-side drawer using its ref -->
            <button class="hide-on-drawer-visible" @click="$refs.leftDrawer.open()">
            <i>menu</i>
            </button>
            <q-toolbar-title :padding="1">
            Title
            </q-toolbar-title>
            <!-- opens right-side drawer using its ref -->
            <button class="hide-on-drawer-visible" @click="$refs.rightDrawer.open()">
                <i>menu</i>
            </button>
        </div>
        <!-- Navigation Tabs -->
        <q-tabs slot="navigation">
            <q-tab icon="mail" route="/layout" exact replace>Mails</q-tab>
            <q-tab icon="alarm" route="/layout/alarm" exact replace>Alarms</q-tab>
            <q-tab icon="help" route="/layout/help" exact replace>Help</q-tab>
        </q-tabs>
        <!-- Left-side Drawer -->
        <q-drawer ref="leftDrawer">
            <div class="toolbar">
            <q-toolbar-title>
                Left Drawer
            </q-toolbar-title>
            </div>
            <div class="list no-border platform-delimiter">
            <q-drawer-link icon="mail" :to="{path: '/', exact: true}">
                Link
            </q-drawer-link>
            </div>
        </q-drawer>
        <!-- IF USING subRoutes only: -->
        <router-view class="layout-view"></router-view>
        <!-- OR ELSE, IF NOT USING subRoutes: -->
        <div class="layout-view"></div>
        <!-- Right-side Drawer -->
        <q-drawer ref="rightDrawer" right-side>
            <div class="toolbar">
            <q-toolbar-title>
                Right Drawer
            </q-toolbar-title>
            </div>
        </q-drawer>
        <!-- Footer -->
        <div slot="footer" class="toolbar">
            This is my footer
        </div>
        </q-layout>
  </div>
</template>
