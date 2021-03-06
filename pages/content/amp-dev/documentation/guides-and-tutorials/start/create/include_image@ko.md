---
$title: 이미지 포함
---

대부분의 HTML 태그는 AMP HTML에 직접 사용될 수 있지만, `<img>` 태그와 같은 특정 태그는 이와 동등하거나 약간 향상된 사용자 지정 AMP HTML 태그로 대체되며, 문제가 있는 몇몇 태그는 즉시 금지됩니다([사양의 HTML 태그]({{g.doc('/content/amp-dev/documentation/guides-and-tutorials/learn/spec/index.md', locale=doc.locale).url.path}}) 참조).

추가적인 마크업이 어떻게 나타나는지를 보여주기 위해, 여기서는 이미지를 페이지에 삽입하는 데 필요한 코드를 보여줍니다.

[sourcecode:html]
<amp-img src="welcome.jpg" alt="Welcome" height="400" width="800"></amp-img>
[/sourcecode]

읽어보기: `<img>`와 같은 태그를 `<amp-img>`로 대체하는 이유와 얼마나 많은 태그를 사용할 수 있는지에 대해 알아보려면, [이미지 및 동영상 삽입]({{g.doc('/content/amp-dev/documentation/guides-and-tutorials/develop/amp_replacements.md', locale=doc.locale).url.path}})으로 이동하세요.

<div class="prev-next-buttons">
  <a class="button prev-button" href="{{g.doc('/content/amp-dev/documentation/guides-and-tutorials/start/create/basic_markup.md', locale=doc.locale).url.path}}"><span class="arrow-prev">이전</span></a>
  <a class="button next-button" href="{{g.doc('/content/amp-dev/documentation/guides-and-tutorials/start/create/presentation_layout.md', locale=doc.locale).url.path}}"><span class="arrow-next">다음</span></a>
</div>

