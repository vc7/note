## Create a Private/Self-Managed CocoaPods Specs

1. Create a specs repo to hold the pods specs.
2. Adding your project repos into the specs repo

<!-- more -->

### Creating a Specs Repo

```sh
mkdir ~/Documents/Private-Cocoapods
cd ~/Documents/Private-Cocoapods
touch README.md
git add README.md
git commit -m "Initial Commit"
git remote add origin https://github.com/username/Private-Cocoapods.git
git push -u origin master
```

will create a repo and host on github, you can make it private or just leave it as private

### Adding to Pod Repo List

The pods repo config folder is located at `~/.cocoapods/repos/`, now we can run `pod repo add` to add your owned specs repo in.

```sh
pod repo add [Private-Cocoapods] https://github.com/username/Private-Cocoapods.git
```

- `[Private-Cocoapods]` - can be any easy-recognized name you want.
- The URL is where the remote repo

Now the basic setting of CocoaPods specs repo is done, lets add something in.

### Adding Pods

As adding pods to [CocoaPods/Specs](https://github.com/CocoaPods/Specs), the process is the same.

```sh
mkdir ~/Documents/Private-Cocoapods/PrivateLibrary
cd ~/Documents/Private-Cocoapods/PrivateLibrary
mkdir 0.0.1
cd 0.0.1
pod spec create PrivateLibrary
```

After the last command, pod will generate a `.podspec` file for you, you will need to [edit the spec](http://guides.cocoapods.org/making/specs-and-specs-repo.html) to fit you library settings

### Tag Your Library

Make version tag to tell cocoapods what to do, and push to github.

```sh
cd /path/to/PrivateLibrary
git remote add origin https://github.com/username/PrivateLibrary.git
git push -u origin master
```

Add the tag to match your podspec in spec repo

```sh
git tag -a 0.0.1 -m "version 0.0.1"
git push origin 0.0.1
```

### Managing Pod Repos

If you want to update or miss-typo want to remove it, you should use following command to do what you want. You can find your pod repo list at `~/.cocoapods/repos/`

#### Update

```sh
pod repo update 'Private-Cocoapods'
```

#### Remove

```sh
pod repo remove 'Private-Cocoapods'
```

### Conclusion

That's it. Have fun! All of above should be worked fine.

### References

- [Private Pods - CocoaPods](http://guides.cocoapods.org/making/private-cocoapods.html)
- [Specs and the Specs Repo - CocoaPods](http://guides.cocoapods.org/making/specs-and-specs-repo.html)
- [Private Cocoapods - Jeffrey Jackson](https://coderwall.com/p/7ucsva)


