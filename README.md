# `Send` Approximation

Some `async fn` state machines are safe to be **sent** across threads, while
others are not. Whether or not an `async fn` `Future` is `Send` is determined
by whether a non-`Send` type is held across an `.await` point. The compiler
does its **best** to approximate when values may be *held* across an `.await`
point, but this analysis is too conservative in a number of places today.
