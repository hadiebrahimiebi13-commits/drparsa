# drparsa

این مخزن نمونه‌ای برای ساخت یک سایت آموزشی چندصفحه‌ای است که با GitHub Pages و GitHub Actions قابل انتشار است.

## معماری پیشنهادی

ساختار پیشنهادی در این ریپازیتوری:

```
repo/
	README.md
	.github/
		workflows/
			pages.yml
	site/
		index.html
		assets/
			css/
				style.css
			js/
				app.js
			img/
		courses/
			medicine/
				index.html
				residency/
					pre-intern/
						ch01/
							index.html
		404.html
```

نکات مهم:

- از لینک‌دهی Relative استفاده کنید (مثال: `../ch02/`).
- همهٔ محتوای قابل انتشار را در پوشهٔ `site/` قرار دهید تا workflow آن را آپلود کند.

## Deploy خودکار با GitHub Actions

فایل workflow نمونه در `.github/workflows/pages.yml` قرار دارد. این workflow از اکشن‌های رسمی `configure-pages`, `upload-pages-artifact` و `deploy-pages` استفاده می‌کند.

برای راه‌اندازی:

1. وارد Settings → Pages شوید و منبع را روی **GitHub Actions** تنظیم کنید.
2. Push کنید؛ workflow به‌طور خودکار محتوی `site/` را دیپلوی می‌کند.

## نحوهٔ افزودن درس/فصل

برای هر فصل یک فولدر بسازید و فایل `index.html` داخل آن قرار دهید تا URL تمیز داشته باشید.

مثال:
`site/courses/medicine/residency/pre-intern/ch01/index.html` -> URL: `.../ch01/`

## فایل‌های ایجادشده در این نمونه

- `site/index.html` — صفحهٔ اصلی نمونه
- `site/404.html` — صفحهٔ خطای 404
- `site/assets/css/style.css` — CSS پایه
- نمونه صفحات در `site/courses/medicine/...`
- workflow: `.github/workflows/pages.yml`

اگر می‌خواهید من برایتان یک تمپلیت کامل‌تر (هدر/فوتر مشترک، CSS پیشرفته RTL، یا SSG مثل Eleventy) بسازم، بگویید تا ادامه دهم.