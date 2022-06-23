# When learning Rust, don't worry about performance.

_2022-06-23_

Learning how to program in Rust should start with getting something to work.
Only later should you work on speed and efficiency.

I started learning Rust by doing the exercises in  the [Rust book](https://doc.rust-lang.org/book/) and [Rustlings](https://github.com/rust-lang/rustlings/).
After that, the next step was to start building projects in Rust.

The domain of Rust applications is systems programming.
With that in mind, I wanted to start by rewriting some familiar tools in Rust:

- `sort`
- `ls`
- `ping`

Rust is known for its speed and memory efficiency.
At the start, I would obsess over these optimizations.
I would try to minimize the number of `.clone()`s.
I would try to minimize heap allocations by avoiding `Vec` and `Box`.
All these were premature optimization.
It took forever to even finish a simple version of my `sort` clone.

I realized that getting a program to _work_ and getting a program to _be efficient_ should be two different stages in software development.
Rust programs can be fast.
But Rust programs can also be slow, and that's okay.
The language gives you capabilities to make slow programs faster, if you so choose.

A Rust program can run as slow as a Python program.
The difference is that making a Python program faster involves diving into C code to create optimizations.

Once I let go of making my Rust program as efficient as possible, I _actually_ finished my `sort` clone.
In the process, I learned a lot more about writing programs in Rust, such as how to use different parts of the standard library.
At this point, I made a few performance optimizations, but not too many.
Eventually, I moved on to working on my `ls` clone.

If I ever wanted to, I can go back to benchmark my `sort` clone and make optimizations.
But that is a different area of learning altogether.

When learning Rust with projects, first make your code work, then make it fast. But not at the same time.
