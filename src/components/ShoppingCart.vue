<template>
	<el-table
    :data="cart"
    stripe
		empty-text="Empty"
    style="width: 100%">
    	<el-table-column
			prop="details.name"
			label="Item"></el-table-column>
		<el-table-column
			label="Unit Price">
			<template scope='scope'>
				{{ scope.row.details.price | currency }}
			</template>
		</el-table-column>
		<el-table-column
			prop="quantity"
			label="Quantity"></el-table-column>
		<el-table-column
    		label="">
    		<template scope="scope">
    			<el-button type="success" icon="plus" @click='addToCart(scope.row.details)' size="mini"></el-button>
    			<el-button type="danger" icon="minus" @click='removeFromCart(scope.row.details.sku)' size="mini"></el-button>
    		</template>
    	</el-table-column>
	</el-table>
</template>

<script>
import {Store} from '../store/Store'

export default {
	computed: {
		cart(){
			return Store.$data.cart
		}
	},
	methods: {
		removeFromCart(sku){
			Store.removeFromCart(sku)
		},
		addToCart(product){
			Store.addToCart(product);
		}
	}
}
</script>
