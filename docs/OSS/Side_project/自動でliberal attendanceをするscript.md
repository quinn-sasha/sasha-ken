
# Requirements
- 高麗大学でのliberal attendanceを自動化する
- 言い換えると、browserでの作業を定めた時間に実行する
- Buttonを押すにはjava scriptが必要かもしれないので、仮の目標は目的のページを開くこと
- Browser: Brave (chrome based)
- OS: Mac

## Easy but not flexible solution
- Chrome extension ([Auto Page Opener](https://chromewebstore.google.com/detail/auto-page-opener/cngkdhdiifcfigdffnmibfopjdlbnpeh))
- Option for chrome based

## Complex but more customizable solution
- Write python script for scheduling task
- Need to install WebDriver to run a program on background

自動でliberal attendanceをする手順
- Open specific url in browser (Brave) at specific time
- May need to login
- Push button to open liberal attendance section (target page)
- Push "attend" button
- Report the attendance
- Done

### Memo
後で見る記事:
- https://stackoverflow.com/questions/54459701/what-is-selenium-and-what-is-webdriver
- https://gist.github.com/passivebot/91d726bafc1f08eb475dd8384a3f21db
- https://realpython.com/modern-web-automation-with-python-and-selenium/
- https://stackoverflow.com/questions/57837496/how-to-use-brave-web-browser-with-python-selenium-and-chromedriver