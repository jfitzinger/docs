---
$title: 이미지 및 동영상 삽입
---

[TOC]

 일반적인 HTML 페이지와 마찬가지로, AMP 에도 **이미지**, **동영상**, "**오디오** 콘텐츠를 삽입할 수 있습니다."

##  왜 `<img>`, `<video>`, `<audio>` 를 사용할 수 없나요?

 AMP 는 `<img>` 와 같이 미디어를 표시하는 기본 HTML 요소를 지원하지 않습니다. 대신 이러한 요소에 해당하는 구성요소를 제공하는데, 그 이유는 다음과 같습니다.

*  애셋이 로드되기 전에 페이지의 레이아웃을 파악해야 하며, 이는 [첫 표시 영역을 미리 로드하는 데 필수적입니다.](/ko/learn/about-how/#size-all-resources-statically)
*  네트워크의 레이지 로드 요청을 제어하고 [리소스의 우선순위를 효과적으로 지정해야 합니다.](/ko/learn/about-how/#prioritize-resource-loading)

주의:  지원되지 않는 &lt;img&gt;, &lt;video&gt;, &lt;audio&gt; 도 렌더링이 됩니다. 하지만 AMP 에서 [페이지를 확인하지]({{g.doc('/content/docs/fundamentals/validate.md', locale=doc.locale).url.path}}) 못하여 AMP 의 다양한 이점을 누릴 수 없게 됩니다.

## 이미지

 다음과 같이 [`amp-img`](/ko/docs/reference/components/amp-img.html) 요소를 사용하여 페이지에 이미지를 삽입합니다.

<!--embedded example - fixed size image -->
<div>
<amp-iframe height="174"
            layout="fixed-height"
            sandbox="allow-scripts allow-forms allow-same-origin"
            resizable
            src="https://ampproject-b5f4c.firebaseapp.com/examples/ampimg.fixed.embed.html">
  <div overflow tabindex="0" role="button" aria-label="Show more">Show full code</div>
  <div placeholder></div>
</amp-iframe>
</div>

이는 가장 기본적인 예로, 이미지는 지정된 높이와 너비로 고정되어 표시됩니다. 최소한 너비와 높이가 명시적으로 설정되어 있어야 합니다.

#### 자바스크립트가 사용 중지되었을 때 이미지 표시

 As `<amp-img>`  는 자바스크립트를 사용하므로, 사용자가 스크립트를 사용 중지한 경우 이미지가 표시되지 않습니다. 이 경우, 다음과 같이 `<img>`, `<noscript>` 를 사용하여 이미지 대신 표시할 내용을 지정해야 합니다.

<!--embedded example - img with noscript -->
<div>
<amp-iframe height="215"
            layout="fixed-height"
            sandbox="allow-scripts allow-forms allow-same-origin"
            resizable
            src="https://ampproject-b5f4c.firebaseapp.com/examples/ampimg.noscript.embed.html">
  <div overflow tabindex="0" role="button" aria-label="Show more">Show full code</div>
  <div placeholder></div>
</amp-iframe>
</div>

### 고급 레이아웃

 AMP 에서는 표준 CSS/HTML 에서보다 훨씬 쉽게 완전 반응형 이미지를 생성할 수 있습니다. 아래는 가장 기본적인 형식으로, `layout="responsive"` 를 추가하기만 하면 됩니다.

<!--embedded example - basic responsive image -->
<div>
<amp-iframe height="193"
            layout="fixed-height"
            sandbox="allow-scripts allow-forms allow-same-origin"
            resizable
            src="https://ampproject-b5f4c.firebaseapp.com/examples/ampimg.basic.embed.html">
  <div overflow tabindex="0" role="button" aria-label="Show more">Show full code</div>
  <div placeholder></div>
</amp-iframe>
</div>

읽어보기: Learn more about [고급 레이아웃 기술]({{g.doc('/content/amp-dev/documentation/guides-and-tutorials/develop/style_and_layout/control_layout.md', locale=doc.locale).url.path}})
에 관해 자세히 알아보세요.

### 동작 및 플레이스홀더

AMP HTML 런타임은 이미지 리소스를 효과적으로 관리하여 표시 영역 위치, 시스템 리소스, 연결 대역폭 등과 같은 요인을 바탕으로 리소스 로드를 지연시킬지 우선할지 선택할 수 있습니다.

읽어보기: [이미지의 대체 내용 및 자리표시자를 제공]({{g.doc('/content/docs/design/responsive_amp/placeholders.md', locale=doc.locale).url.path}}) 하는 방법에 관해 자세히 알아보세요.


## 애니메이션 이미지

 The [`amp-anim`](/ko/docs/reference/components/amp-anim.html) 요소는 `amp-img` 요소와 아주 유사하며, GIF 와 같은 애니메이션 이미지의 로드 및 재생을 관리하는 추가 기능을 제공합니다.

<!--embedded amp-anim basic example -->
<div>
<amp-iframe height="253"
            layout="fixed-height"
            sandbox="allow-scripts allow-forms allow-same-origin"
            resizable
            src="https://ampproject-b5f4c.firebaseapp.com/examples/ampanim.basic.embed.html">
  <div overflow tabindex="0" role="button" aria-label="Show more">Show full code</div>
  <div placeholder></div>
</amp-iframe>
</div>

참고: 이 구성요소를 사용하려면` <script async custom-element="amp-anim" src="https://cdn.ampproject.org/v0/amp-anim-0.1.js"></script>` 를 페이지 헤드에 삽입하세요.

## 동영상

 페이지에 동영상을 삽입하려면 [`amp-video`](/ko/docs/reference/components/amp-video.html) 요소를 사용합니다.

 직접 HTML5 동영상 파일 삽입에만 이 요소를 사용하세요. 이 요소는 `src` 속성으로 지정한 비디오 리소스를 AMP 가 결정한 시간에 레이지 로드합니다.

동영상이 시작하기 전에 플레이스홀더를 삽입하고, 브라우저에서 HTML5 동영상을 지원하지 않는 경우 대체할 내용을 삽입합니다. 예를 들면 다음과 같습니다.

<!--embedded video example  -->
<div>
<amp-iframe height="234"
            layout="fixed-height"
            sandbox="allow-scripts allow-forms allow-same-origin"
            resizable
            src="https://ampproject-b5f4c.firebaseapp.com/examples/ampvideo.fallback.embed.html">
  <div overflow tabindex="0" role="button" aria-label="Show more">Show full code</div>
  <div placeholder></div>
</amp-iframe>
</div>

## 오디오

 페이지에 오디오 리소스를 삽입하려면 [`amp-audio`](/ko/docs/reference/components/amp-audio.html) 요소를 사용합니다.

 직접 HTML5 오디오 파일 삽입에만 이 요소를 사용하세요. AMP 페이지에 삽입되는 모든 외부 리소스와 같이, 이 요소는 `src` 속성으로 지정한 오디오 리소스를 AMP가 결정한 시간에 레이지 로드합니다.

오디오가 시작하기 전에 플레이스홀더를 삽입하고, 브라우저에서 HTML5 오디오를 지원하지 않는 경우 대체할 내용을 삽입합니다. 예를 들면 다음과 같습니다.

<!--embedded audio example  -->
<div>
<amp-iframe height="314"
            layout="fixed-height"
            sandbox="allow-scripts allow-forms allow-same-origin"
            resizable
            src="https://ampproject-b5f4c.firebaseapp.com/examples/ampaudio.basic.embed.html">
  <div overflow tabindex="0" role="button" aria-label="Show more">Show full code</div>
  <div placeholder></div>
</amp-iframe>
</div>

참고: 이 구성요소를 사용하려면 `<script async custom-element="amp-audio" src="https://cdn.ampproject.org/v0/amp-audio-0.1.js"></script>` 를 페이지 헤드에 삽입하세요.