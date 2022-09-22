[![Twitter](https://img.shields.io/badge/Twitter-@Vosough_k-blue.svg?style=flat-square)](https://twitter.com/vosough_k)
[![Linkedin](https://img.shields.io/badge/Linkedin-KiarashVosough-blue.svg?style=flat-square)](https://www.linkedin.com/in/kiarashvosough/)

Build DocC Static Site: Build Static Site From DocC Archive, Document Your Project Like A Professional On Github Action

- [Requirements](#requirements)
- [Usage](#usage)
- [Integration](#integration-with-github-pages-deployment)
- [Contributors](#contributors)
- [License](#license)

## Requirements

| Platform | Minimum Swift Tools Version | Status |
| --- | --- | --- |
| macOS 12.0+ | 5.5 | Tested |

## Usage

See [action.yml](https://github.com/kiarashvosough1999/build-docC-static-site/blob/master/action.yml).

> Make sure to set the version to latest tag.

As An Example:

```yml
name: worksapce
on:
  push:
    branches:
      - '**'
jobs:
  build_docC:
    runs-on: macos-12
    steps:
    - name: checkout
      uses: actions/checkout@v3
      with:
       repository: ${{ github.event.pull_request.head.repo.full_name }}
       ref: ${{ github.event.pull_request.head.ref }}

    - name: build static site
      uses: actions/build-docC-static-site@v1.0.2
```

## Integration With Github Pages Deployment

You can use [docC-github-pages-deploy
](https://github.com/kiarashvosough1999/docC-github-pages-deploy/tree/master) to deploy generated static site from docC to **Github-Pages**.

> The default `docC-generated-static-site-uploaded-name` associated with [docC-github-pages-deploy
](https://github.com/kiarashvosough1999/docC-github-pages-deploy/tree/master) and `docC-generated-static-site-zipped-upload-name` associated with this action, input must be the same.

> This action will zip the generated static site with `gtar` and `tar` extension. So do not specify the zip extension on either `docC-generated-static-site-uploaded-name` or `docC-generated-static-site-zipped-upload-name`.
 
## Contributors

Feel free to share your ideas or any other problems. Pull requests are welcomed.

## License

CocoAttributedStringBuilder is released under an MIT license. See [LICENSE](https://github.com/kiarashvosough1999/build-docC-static-site/blob/master/LICENSE) for more information.
