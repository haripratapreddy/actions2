# actions2
Trial actions demo
readme1
readme2.1
changes for pr steps

readme3
readme4
readme5
readme hari


name: Deploy GitHub Pages

on:
  release:
    types: [published]

jobs:
  build-and-deploy:
    runs-on: ubuntu-latest

    steps:
    - name: Checkout code
      uses: actions/checkout@v2

    # Add any other setup steps required by your project here

    - name: Deploy to GitHub Pages
      uses: peaceiris/actions-gh-pages@v4
      with:
        github_token: ${{ secrets.GITHUB_TOKEN }}
        publish_dir: ./  # Adjust this to your build output directory
        publish_branch: gh-pages  # The branch to publish to
        destination_dir: ${{ github.event.release.tag_name }}
