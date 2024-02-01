## PNPM Git Resolver Issue: Incorrect Branch Installation

When specifying a Git dependency in `package.json`, PNPM unexpectedly installs the `master` branch instead of the explicitly declared `empty` branch. This behavior contrasts with Yarn, which accurately installs the specified `empty` branch for the `react-native-camera-kit` dependency. This inconsistency in PNPM's interpretation of Git URLs compared to Yarn can lead to potential confusion and errors in dependency management.

### Understanding the Issue

The `package.json` declaration for installing a Git dependency is as follows:

```json
"dependencies": {
  "react-native-camera-kit": "git+https://gitlab.com/dung.huynh1/react-native-camera-kit.git#empty"
}
```

This line instructs the package manager to clone the react-native-camera-kit repository from the specified GitLab URL, specifically targeting the empty branch. While Yarn follows this directive accurately, PNPM diverges by defaulting to the repository's main branch (commonly master), ignoring the branch specifier in the URL.
