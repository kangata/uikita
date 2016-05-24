<template lang="jade">
	ul.uk-list.uk-list-line
		li(v-for="list in lists", @click="itemClick(list.key)")
			.uk-list--md-item
				.uk-list--md-item-icon(:style="{ background: randBg() }")
					span {{ list.icon }}
				.uk-list--md-item-content
					h3 {{ list.title }}
					span {{ list.meta }}
</template>

<script>
	export default {
		props: ['lists'],
		data () {
			return {
				materialColors: [
					{ name: 'red', code: '#f44336' },
					{ name: 'pink', code: '#E91E63' },
					{ name: 'purple', code: '#9C27B0' },
					{ name: 'deepPurle', code: '#673AB7' },
					{ name: 'indigo', code: '#3F51B5' },
					{ name: 'blue', code: '#2196F3' },
					{ name: 'lightBlue', code: '#03A9F4' },
					{ name: 'cyan', code: '#00BCD4' },
					{ name: 'teal', code: '#009688' },
					{ name: 'green', code: '#4CAF50' },
					{ name: 'lightGreen', code: '#8BC34A' },
					{ name: 'lime', code: '#CDDC39' },
					{ name: 'yellow', code: '#FFEB3B' },
					{ name: 'amber', code: '#FFC107' },
					{ name: 'orange', code: '#FF9800' },
					{ name: 'deepOrange', code: '#FF5722' },
					{ name: 'brown', code: '#795548' },
					{ name: 'grey', code: '#9E9E9E' },
					{ name: 'blueGrey', code: '#607D8B' }
				]
			}
		},
		methods: {
			randBg: function () {
				return this.materialColors[Math.floor(Math.random() * 18)].code
			},
			itemClick: function (key) {
				this.$dispatch('itemOnClick', key)
			}
		}
	}
</script>