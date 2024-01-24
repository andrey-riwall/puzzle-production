<template>
	<div class="container">	
		<ModelList
			@choice_item="choiceItem"
			:items="items"
		/>
		<ModelForm
			:item="currentItem"
			@update_list="editList"
		/>
	</div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import ModelForm from '@/components/ModelForm.vue';
import ModelList from '@/components/ModelList.vue';

import { Model } from '@/types/types';

interface State {
  items: Model[];
	current_item: Model | undefined;
}

export default defineComponent({
	components: {
		ModelForm: ModelForm,
		ModelList: ModelList
	},
	data() : State {
		return { 
			items: [
        {
          customer_id: "user1",
          server_name: "server1",
          server_type: "type1"
        },
        {
          customer_id: "user2",
          server_name: "server2",
          server_type: "type2"
        },
        {
          customer_id: "user3",
          server_name: "server3",
          server_type: "type3"
        },
        {
          customer_id: "user4",
          server_name: "server4",
          server_type: "type4"
        },
        {
          customer_id: "user5",
          server_name: "server5",
          server_type: "type5"
        },
        {
          customer_id: "user6",
          server_name: "server6",
          server_type: "type6"
        },
      ],
			current_item: undefined
		};
	},
	computed: {
		currentItem() {
			return this.current_item ? this.current_item : this.items[0];
		}
	},
	methods: {
		choiceItem(item: Model) {
			this.current_item = item;
		},
		editList(newItem: Model) {
			const id = this.items.findIndex((item) => item.customer_id === newItem.customer_id);
			this.items[id] = newItem;
			alert('Change completed');
		}
	}
});
</script>

<style lang="scss">
	@import url('https://fonts.googleapis.com/css2?family=Poppins:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;0,700;0,800;0,900;1,100;1,200;1,300;1,400;1,500;1,600;1,700;1,800;1,900&display=swap');
	@import url('https://fonts.googleapis.com/css2?family=JetBrains+Mono:ital@0;1&display=swap');

	* {
		box-sizing: border-box;
		padding: 0;
		margin: 0;
		list-style: none;
		text-decoration: none;
		font-family: "Poppins", sans-serif;
		font-weight: 400;
	}

	body {
		position: relative;

		display: flex;
		align-items: center;
		justify-content: center;

		padding: 100px 0;
		min-height: 100dvh;
	}

	button {
		background: none;
		border: none;
		outline: none;
		cursor: pointer;
	}

	input, select {
		background: none;
		border: none;
		outline: none;
	}

	.scroll::-webkit-scrollbar {
		width: 16px;
	}
	.scroll::-webkit-scrollbar-track {
		background: transparent;
	}
	.scroll::-webkit-scrollbar-thumb {
		background-color: rgba(black, .05);
		border-radius: 20px;
		border: 5px solid white;
	}

	.container {
		display: grid;
		grid-template-columns: 1fr 1fr;
		grid-gap: 70px;

		width: 1200px;
	}

	.card {
		width: 100%;

    background: rgba(black, .03);
    border-radius: 25px;
		padding: 50px 30px;
  }

	.heading {
		font-weight: 500;
		font-size: 30px;
		margin-bottom: 10px;
	}
</style>
