+++
blogimport = true
date = 2013-09-01T22:14:00Z
image = "/images/white_mountain.jpg"
image_gallery = []
images = ["/images/mvimg_20190825_082545.jpg", "/images/mvimg_20190825_075709.jpg", "/images/mvimg_20190824_121100.jpg"]
tags = ["Zenotag"]
title = "Zeno"
type = "post"
updated = "2020-04-06T17:07:25.000+00:00"
[author]
name = "ann-lauriene"
uri = ""

resources:
- src: "gallery/*.jpg"
  name: gallery-:counter
  title: gallery-title-:counter
+++


Hallo This is miy blog position
{{< gallery folder="gallery" title="masonary-post" >}}


{{ with .Get "title" }}
  <h4>{{ . }}</h4>
{{ end }}
  <div class="gallery" itemscope itemtype="http://schema.org/ImageGallery">
  {{- range (.Page.Resources.Match (printf "%s*" (.Get "folder"))) }}
  {{ $thumbnail := .Resize "320x" }}
    <figure itemscope itemtype="http://schema.org/ImageObject" class="image gallery-item">
    <a href="{{ .Permalink }}" itemprop="contentUrl" data-size="{{ .Width }}x{{ .Height }}" >
      <img src="{{ $thumbnail.Permalink }}" itemprop="thumbnail" alt="galleryImage" class="galleryImage" />
    </a>
    <figcaption itemprop="caption description">
      <span itemprop="copyrightHolder"></span>
    </figcaption>
    </figure>
  {{ end }}
  </div>
