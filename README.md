# Ask for help with an $100 offer

I'm seeking for help for that issue with $100 offer, not very much, but hope anyone could help! Pls send me message if you can help, I will pay for that. Very appreciate it!

## Issue: 
> using `git2-rs` in multiple threads env makes old files in git repository deleted, even I use a lock to prevent accessing a repo at the same time, the reason might be that `libgit2` doesn't work well in multiple thread environment. But even the files creating do not happen at the same time, it always make the old files deleted, then only one file left at the end.

## Target:
> It creates files correctly in multiple threads env, no old files deleting.

## Tips:
1. There is a `test_create_file_and_commit` test function in `main.rs`, which try to create files in a git `bare` repository.
2. There is a function `test_create_file_and_commit` in `main.rs`, it tris to call `create_file_then_commit_then_push` from a multiple thread environment, it can't get success too.
4. In my implementation it creates files in `bare` repository by using `index.add_frombuffer` and `repo.commit` of `git2-rs` 

![img](https://camo.githubusercontent.com/d4f9104ac467d8298fb9264c7e199daca2b1f0bb/68747470733a2f2f692e696d6775722e636f6d2f753158483658382e706e67)
![img1](https://camo.githubusercontent.com/fdd9ffbc7a41cc303797b775b83ea7cb12847ffa/68747470733a2f2f692e696d6775722e636f6d2f625168756f6a312e706e67)