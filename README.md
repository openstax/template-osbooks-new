# template-osbooks-new
Template repository for creating a new osbook

Use this repository template to create an "osbooks" repository for a new book. If you instead need to create a repository for migrating an exiting book from CNX, use [template-osbooks](https://github.com/openstax/template-osbooks).

### Overview of Steps

1. **Create osbook repository** - by using this template repository.
2. **Customize files for new book** - by editing `collections/template.collection.xml`, `META-INF/book-slug.xml`, and `canonical.json`.
3. **Test your book in Gitpod** - open the book inside Gitpod, try adding modules and subcollections to ensure that it works.

---

## Create osbook repository

1. On GitHub, navigate to the main page of this repository.
2. Above the file list, click **Use this template**.
3. In the _Owner_ drop-down menu, select **openstax**.
4. Name the Repository:

   - _osbooks-**book-name**_, if repo contains only one collection, or
   - _osbooks-**book-name**-bundle_, if repo contains more than one collection

   Note: Repository names can be changed at a later time. _Description_ can be left blank.

5. Set repository visibility to **Private**.

6. Leave **Include all branches** unchecked, this template repository only has one branch.

7. Click **Create repository from template**.

## Customize files for new book

1. Edit the `collection/template.collection.xml'
    
    -rename the file by replacing `template` in the filename with the book slug (eg. `university-physics-volume-1.collection.xml`).
        - if the repo is for a bundle (contain multiple books), each book will require their own collection.xml file.
    - inside the file replace:
        - the title in the `<md:title>` field
        - the slug in the `<md:slug>` field
        - and if necessary, the license in the `<md:license>` field
2. Edit the `META-INF/books.xml`
    - replace `template.collection.xml` in the `<book>` field with the name of the file created in step 1
        - if this repo is for a bundle, each book will require their own `<book>` field, directing too the associated `collection.xml`
3. Edit the `canonical.json
    - add the slug to the list.
        - if this repo is for a bundle, each book slug will need to be added to the list.
