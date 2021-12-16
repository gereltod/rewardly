# Сервер дээрх мэдээлэл шинэчлэх

[![Build Status](https://travis-ci.org/joemccann/dillinger.svg?branch=master)](https://travis-ci.org/joemccann/dillinger)

Reactjs app, react-admin хийгдсэн системүүд юм.
Үндсэн сервис/production болоход дараах системүүд оролцож байгаа.
- Gitlab runner
- Google Build
- Google Container Registry
- Google Run
- ✨Rewardly.app✨

 _FILE_
- [.gitlab-ci.yml](https://gitlab.com/Sodtseren/reeward-customer/-/blob/production/.gitlab-ci.yml) -> stage prod
- [cloudbuild.yaml](https://gitlab.com/Sodtseren/reeward-customer/-/blob/production/cloudbuild.yaml) -> build -> image -> push - > run



```sh
git checkout production
git pull origin development
git push 
//командын дараа gitlab дээрх trigger ажиллаж эхэлнэ.
```

Google cloud орчинд дараах өөрчлөлтүүд бий болно... 
Дундаж хугацаа 10 минут үргэлжлэнэ.

- [Goolge Build](https://console.cloud.google.com/cloud-build/builds?project=reeward-production) хамгийн эхэнд running процесс дотор лог бичигдэж байгаа.
- [Google Container Registry](https://console.cloud.google.com/gcr/images/reeward-production?project=reeward-production) энэ дотор latest гэсэн хамгийн сүүлийн docker image хуулагдана.
- [Goolge Run](https://console.cloud.google.com/run/detail/asia-southeast1/reeward-customer/revisions?project=reeward-production) бүх үйлдэл дарааллын дагуу зөв алдаагүй явбал revision дээр нэмэгдэж тэрхүү солигдоно.


> Санамж: `--timout=10m` лог удаан хараад нойр хүрвэл [дар](https://www.youtube.com/watch?v=G1IbRujko-A).

