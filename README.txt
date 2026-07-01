HOW IMAGES WORK ON THIS SITE
=============================

Nothing needs to be edited in the code — just drop image files into
the right folder with the right filename, and they show up automatically.
Until a file is added, that spot shows a dashed placeholder box telling
you exactly what filename belongs there.

1) SITE-WIDE IMAGES (put directly in /images)
--------------------------------------------
hero.jpg              → Hero banner, top of homepage   (1920x1080 recommended)
cat-machines.jpg      → "Espresso Machines" category tile (1000x1050)
cat-grinders.jpg      → "Coffee Grinders" category tile    (1000x1050)
cat-blenders.jpg      → "Blenders" category tile            (1000x1050)
cat-accessories.jpg   → "Accessories" category tile         (1000x1050)
cat-consumables.jpg   → "Consumables" category tile          (1000x1050)
svc-barista.jpg       → "Barista 101 Training" service card (800x600)
svc-menu.jpg          → "Menu & Product Development" card    (800x600)
svc-menu-staff.jpg    → "Menu Dev + Staff Training" card     (800x600)

2) PRODUCT PHOTOS (put directly in /diagrams — no subfolders)
-----------------------------------------------------------
This folder is flat, so every file needs a unique name. The naming
pattern is: <product-id>-<photo-number>.jpg

  diagrams/esp-classic-1.jpg          Classic Single-Group Espresso Machine, photo 1
  diagrams/esp-classic-2.jpg          ...photo 2
  diagrams/esp-classic-3.jpg          ...photo 3
  diagrams/esp-duo-1.jpg              Twin-Group Commercial Espresso Machine
  diagrams/esp-duo-2.jpg
  diagrams/esp-duo-3.jpg
  diagrams/grind-conical-1.jpg        Conical Burr Grinder
  diagrams/grind-conical-2.jpg
  diagrams/grind-conical-3.jpg
  diagrams/grind-flat-1.jpg           Flat Burr Espresso Grinder
  diagrams/grind-flat-2.jpg
  diagrams/grind-flat-3.jpg
  diagrams/blend-bar-1.jpg            Bar Blender Pro
  diagrams/blend-bar-2.jpg
  diagrams/blend-bar-3.jpg
  diagrams/blend-commercial-1.jpg     Commercial Blender XL
  diagrams/blend-commercial-2.jpg
  diagrams/blend-commercial-3.jpg
  diagrams/acc-tamper-1.jpg           Tamper & Tamping Mat Set
  diagrams/acc-tamper-2.jpg
  diagrams/acc-pitcher-1.jpg          Milk Pitcher Set (3 Sizes)
  diagrams/acc-pitcher-2.jpg
  diagrams/cons-syrup-1.jpg           Flavor Syrup Bundle
  diagrams/cons-syrup-2.jpg
  diagrams/cons-beans-1.jpg           House Blend Coffee Beans, 1kg
  diagrams/cons-beans-2.jpg

If you already have image files with different names, either rename them
to match the list above, or open index.html and product.html, find the
matching product's "images:" line, and type your actual filenames in
there instead (they need to be updated in BOTH files, since the JS is
merged into each page rather than shared from one file).

3) ADDING OR EDITING PRODUCTS
------------------------------
Product data now lives directly inside index.html and product.html
(inside the <script> tag near the top of each file's JS). Each product
is a block like:

  {
    id: "esp-classic",              <- used in the URL: product.html?id=esp-classic
    name: "...",
    category: "machines",            <- must match a key in CATEGORIES
    price: 68000,
    salePrice: 59900,                <- set to null if not on sale
    badge: "Best Seller",            <- "Sale", "New", "Best Seller", or null
    images: ["esp-classic-1.jpg", "esp-classic-2.jpg", "esp-classic-3.jpg"],
    specs: { "Type": "Semi-automatic", ... },
    description: "..."
  }

IMPORTANT: because the JS is embedded in both pages, any change to a
product (price, specs, images, description) needs to be made in BOTH
index.html and product.html to keep them in sync.

Copy an existing block, change the values, give it a new "id", and add
your image files to /diagrams following the naming pattern above (or
your own chosen filenames). It will automatically appear in the catalog
grid, the filter tabs, and get its own product.html?id=... page.

4) YOUR MESSENGER LINK
------------------------
Near the top of the JS in both index.html and product.html:

  const MESSENGER_USERNAME = "yourpagename";

Replace "yourpagename" with your real Facebook Page username in BOTH
files. Every "Inquire Now" / "Message Us" button on the site uses this
automatically.

Tip: keep image file sizes reasonable (under ~500KB each, JPG or WebP)
so the pages load fast.