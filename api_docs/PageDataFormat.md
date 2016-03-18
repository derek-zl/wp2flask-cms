## 文章列表(无分类信息):

```python
post_dict_list = [
    dict(
        id=p.id,
        title=p.title,
        slug=p.slug,
        cslug=p.category.cslug,
    )
    for p in posts
]
```

## 文章列表(含分类信息)

```python
cate_posts_list = dict(
    id=c.id,
    name=c.name,
    slug=c.slug,
    post_count=c.posts.count(),
    plist=[
      dict(
          id=p.id,
          title=p.title,
          slug=p.slug,
      )
      for p in posts
    ],
)
```
## 分类列表

```python
  cate_dict_list = [
    dict(
      id=c.id,
      name=c.name,
      slug=c.slug,
      post_count=c.posts.count()
    )
    for c in cates
  ]
```

## 首页推荐
```python
  plist = [
    dict(
      id=p.id,
      title=p.title,
      slug=p.slug,
      cslug=p.category.slug,
      brief=briefy(p.body, 120),
    )
    for p in posts
  ]
```

## 标签部件
```python
  tag_dict_list = [
    dict(
      id=t.id,
      name=t.name,
      slug=t.slug,
      font_size=tag_font_size(t.posts.count()),
    )
    for t in tags
  ]
```