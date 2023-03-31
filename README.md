
## Filtering data with computed(title)

````typescript
<script setup>
import data from "./data";
const sortBy = ref("");
const order = ref("asending");
const title = ref("");
const products = ref(data);
// console.log(data);
const filteredProducts = computed(() => {
  if (title.value) {
    return [...products.value].filter((item) => {
      return title.value
        .toLocaleLowerCase()
        .split(" ")
        .every((v) => item.title.toLocaleLowerCase().includes(v));
    });
  } else {
    return products.value;
  }
});
</script>
`````


Web site: https://filter-products-vue.netlify.app/
