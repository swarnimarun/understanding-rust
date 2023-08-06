
## dyn with a bit of impl

```rust
Swarnim Arun
Rust Engineer @ DeepSource
```

---

## about me

- Swarnim Arun, work as Rust Engineer
- I mostly work on system's programming things, think compilers, analysis tools, etc.
- I also have and love to work with graphics programming, game engines and such things.
- Languages I generally work with: Rust, C++, Zig, Typescript, Haskell 

---

```qrcode
https://www.github.com/swarnimarun/understanding-rust
```

---

## so what is dyn?

dyn is a feature of Rust programming language, that allows us to use "dynamic-polymorphism" to simplify the code we write. 

```rust
use std::error::Error;
fn main() -> Result<(), Box<dyn Error>> {
    Ok(())
}
```

---

## no really what is dyn?

dyn is the only way to create trait objects in Rust as of 2021 edition, due to bare_trait_objects.

---

## cool! but what are trait objects?

Well, trait objects are types that allow us to define general behaviour, but where the specific action is unknown until runtime.

---

## hmmm... how does that work?

A trait object points to both an instance of a type implementing our specified trait and a table used to look up trait methods on that type at runtime.

Also popularly called as the vtable.

---

## so same as the c++ overloading?

Pretty much, here rather than overloading the data, we just overload the behaviour, similar to interfaces.

But there is a major catch compared to C++ regarding trait objects in Rust.

---

## let me guess, rust is "safe"-er?

Yep correct again, in Rust dyn can only be used when a trait is "object-safe".

---

## now what is object-safety?

object-safety is defined in several Rust rfcs, and lists the constraints for cases where you can't create an object of a trait.

ref link: https://doc.rust-lang.org/reference/items/traits.html#object-safety

---

## what are the rules?

The general rules are:

- If the trait depends on Sized.
- If Self is used as a trait function parameter or in return type.

- And a few other cases related to above, look at the link from previous slide.

---

## can we not use impl for something similar no?

Seems so,

```rust
trait Printable {
    fn print(&self) {
        println!("from Printable");
    }
}

impl<K> Printable for K {} 

fn t(t: impl Printable) {
    t.print();
}

fn main() {
    let v: &dyn Printable = &32;
    t(v);
}
```

---

## how are the two different?

...

---

```md
============
=== code ===
=== -ing ===
=== time ===
============
```

---

## Thank You


# github
https://github.com/swarnimarun

# website
https://swarnimarun.com

# email
swarnimarun11@gmail.com

# twitter
https://twitter.com/swarnimarun

# telegram
https://t.me/minraws
