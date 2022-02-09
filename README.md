# template-osbooks-new
Template repository for creating a new osbook

Use this repository template to create an "osbooks" repository for a new book. If you instead need to create a repository for migrating an exiting book from CNX, use [template-osbooks](https://github.com/openstax/template-osbooks).

### Overview of Steps

1. **Create osbook repository** - by using this template repository.
2. **Customize files for new book** - by editing `collections/template-slug.collection.xml`, `META-INF/books.xml`, and `canonical.json`.
3. **Add user permissions*** - allow people to edit the book.
4. **Test your book in Gitpod** - open the book inside Gitpod, try adding modules and subcollections to ensure that it works.

---

## Create osbook repository

1. On GitHub, navigate to the main page of this repository (you're probably already here).
2. Above the file list, click **Use this template**.![Screen Shot 2021-07-20 at 7 24 56 AM](https://user-images.githubusercontent.com/30244554/126341590-baae4973-d518-4106-b41c-5c94b5018eb4.png)

3. In the _Owner_ drop-down menu, select **openstax**.
4. Name the Repository:

   - _osbooks-**book-name**_, if repo contains only one collection, or
   - _osbooks-**book-name**-bundle_, if repo contains more than one collection

   Note: Repository names can be changed at a later time. _Description_ can be left blank.

5. Set repository visibility to **Private**.

6. Leave **Include all branches** unchecked, this template repository only has one branch.

7. Click **Create repository from template**.![Screen Shot 2021-07-20 at 7 29 48 AM](https://user-images.githubusercontent.com/30244554/126342661-14938829-bd1a-4bf6-b6d2-48f2dedf4d47.png)


## Customize files for new book

1. Once the repository is created, navigate to the `COLLECTIONS` folder. Edit the `collection/template-slug.collection.xml`
    
    - rename the file by replacing `template-slug` in the filename with the created book slug (eg. `university-physics-volume-1.collection.xml`).
        - if the repo is for a bundle (contain multiple books), each book will require their own collection.xml file.
    - inside the file replace:
        - the uuid with in the `<md:uuid>` field with one generated [here](https://www.uuidtools.com/v4) (Note to CM's: make sure to add this to cnx password sheet)
        - the title in the `<md:title>` field
        - the slug in the `<md:slug>` field
        - and if necessary, the license in the `<md:license>` field
        - the collection number in the `<md:content-id>` field (Note to CM's: make sure to add this to cnx password sheet)
        - the language code in the `<md:language>` field. (`en` for english, `pl` for polish, or `sp` for spanish)
    ![Screen Shot 2021-07-20 at 7 36 30 AM](https://user-images.githubusercontent.com/30244554/126344043-27c4b5aa-c2e9-421b-a3e6-60ca95cd39ef.png)
    - commit changes

2. Navigate to the `META-INF` folder, and edit the `META-INF/books.xml`
    - replace `template.collection.xml` in the `<book href="">` field with the name of the file created in step 1
    - replace the book slug in the `<book slug="">` field
        - if this repo is for a bundle, each book will require their own `<book>` field, directing too the associated `collection.xml`
    ![Screen Shot 2021-07-20 at 7 45 29 AM](https://user-images.githubusercontent.com/30244554/126344715-395b1ab9-9e23-400a-92f1-f903b7d605e3.png)
    - commit changes

3. Navigate to the `CANONICAL.JSON` file and edit the `canonical.json`
    - add the created slug to the list.
        - if this repo is for a bundle, each book slug will need to be added to the list.
    ![Screen Shot 2021-07-20 at 7 47 20 AM](https://user-images.githubusercontent.com/30244554/126344968-91721928-202c-459c-ab6f-48ae32ec1cb4.png)
    - commit changes

4. Navigate to the `LICENSE` file and Copy/Paste one of the following into `LICENSE` file:

   - [CC-BY 4.0](https://github.com/openstax/content-synchronizer/blob/main/licenses/by-4.0)
   - [CC-BY-NC-SA 4.0](https://github.com/openstax/content-synchronizer/blob/main/licenses/by-nc-sa-4.0)
   - [CC-SA 4.0](https://github.com/openstax/content-synchronizer/blob/main/licenses/by-sa-4.0)
   - commit changes

## Add user permissions

1. Change permissions with manage permissions
   1. On GitHub, navigate to the main page of this repository.
   2. On top navigation tabs, click **Settings**.
   3. On left navigation, click **Manage access**.
   4. Using the Manage Acccess panel, click the green "Invite Teams or People" to add the following teams, making sure they each have the proper role indicated below:
      - openstax/ce-all, Role: Write
      - openstax/content-managers, Role: Admin
      - openstax/ce-admins, Role: Admin
      - openstax/katalyst, Role: Read
      - {vendor account}, Role: Write (Note: find the book's vendor under column C [here](https://docs.google.com/spreadsheets/d/1dVpPsE2wTIZyoC4n8GnooqpntC2IZDTjcSdNMPycfB0/edit#gid=254689054)).
         - Wisewire: `ww-openstax`
         - MPS: `mps-openstax`
         - Six Red Marbles (SRM): `srm-openstax`
        
![User Permissions](https://user-images.githubusercontent.com/8730430/133662150-76513e6a-ee23-44bf-b5b8-119f721ca3d7.png)

## Final Steps

1. Open the book inside Gitpod by clicking the green gitpod button in the main book's repo. Click view using github. Try adding test modules and a test subcollection in the ToC editor to test if POET can parse the files correctly.
2. Create a card for the on [Content Engineering Tech Team board](https://github.com/openstax/cnx/issues/new?assignees=&labels=&template=task.md)
   - Issue Title: review new repository for osbook-new-book-name
   - Include link to new repository
   - Include finalization date (when repo is needed by)
