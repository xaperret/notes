---
date updated: 2021-10-21 17:33
---

Topic:
Tags: #review #pn_2_1
Links:
Date Created: 21-10-21

---

# SetOnClickListener

## SetOnClickListener in few words

## SetOnClickListener in details

There are five ways to use SetOnClickListener:

**First:**

```kotlin
button.setOnClickListener {
    // Do some work here
}
```

**Second:**

```kotlin
button.setOnClickListener(object : View.OnClickListener {
    override fun onClick(view: View?) {
        // Do some work here
    }

})
```

**Third:**

```kotlin
button.setOnClickListener(View.OnClickListener { view ->
    // Do some work here
})
```

**Forth:**

```kotlin
class MainActivity : AppCompatActivity(), View.OnClickListener{

    lateinit var button : Button

    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_main)
        button = findViewById(R.id.button1)
        button.setOnClickListener(this)
    }

    override fun onClick(view: View?) {
        when(view?.id){
            R.id.button1->{
                // do some work here
            }
        }
    }
}
```

**Fifth:**

```kotlin
class MainActivity : AppCompatActivity(){

    lateinit var button : Button

    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_main)
        button = findViewById(R.id.button1)
        button.setOnClickListener(listener)
    }

    val listener= View.OnClickListener { view ->
        when (view.getId()) {
            R.id.button1 -> {
                // Do some work here
            }
        }
    }
}
```

## References

- <https://stackoverflow.com/questions/44301301/android-how-to-achieve-setonclicklistener-in-kotlin>
