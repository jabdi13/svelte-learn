<script>
  let numbers = [1, 2, 3, 4];
  const obj = { foo: { bar: 1 } };
  const foo = obj.foo;

  function addNumber() {
    // numbers.push(numbers.length + 1);
    // Idiomatic solution
    numbers = [...numbers, numbers.length + 1];
  }

  function updateObj() {
    // This won't trigger reactivity on obj.foo.bar
    // foo.bar = 2
    // Unless you assign it like this
    // obj = obj
    // or this
    obj.foo.bar = 2;
  }

  $: sum = numbers.reduce((total, currentNumber) => total + currentNumber, 0);
</script>

<p>{numbers.join(" + ")} = {sum}</p>

<button on:click={addNumber}> Add a number </button>

<p>bar = {obj.foo.bar}</p>

<button on:click={updateObj}> Update obj </button>
