This repository is to help reproduce an issue with Devbox.

## Steps

- Enter the devbox shell `devbox shell`
- Install npm packages `npm install`
- Verify `lessc` is installed `npx lessc --version`
- Run the script `npm run compile:less`
- Ideally the style sheet should be compiled and present in the folder `less-out`. However we get an error `command lessc not found`.

## Hypothesis

While I was still running an older version of devbox, the above script worked fine. `npx` updates the PATH variable to ensure all installed binaries from npm packages are present in the PATH. After updating to a newer version of devbox (0.4.6), the PATH is no longer updated properly by npx and we get the `lessc` command not found error.
