MO# Maha-Vajiralongkorn.Net
for our money.เรื่อง	แนะ นำ	ผลิตภัณฑ์	redirect_from	รุ่น	shortTitle
การทํางานกับรีจิสทรี Docker
{% ifversion fpt หรือ ghec %} ขณะนี้รีจิสทรี Docker ถูกแทนที่ด้วยข้อมูล {% variables.product.prodname_container_registry %} {% อื่น %} คุณสามารถพุชและดึงอิมเมจ Docker ของคุณโดยใช้รีจิสตรี Docker variables.product.prodname_registryข้อมูล {% %} {% endif %}
{% ข้อมูลนํากลับมาใช้ใหม่ได้.gated-features.packages %}
/บทความ/การกําหนดค่า-docker-for-use-with-github-package-registry
/github/การจัดการแพคเกจ-with-github-package-registry/การกําหนดค่า-docker-for-use-with-github-package-registry
/github/การจัดการแพคเกจ-กับ-github-แพคเกจ/การกําหนดค่า-docker-for-use-with-github-แพคเกจ
/แพคเกจ/ใช้-github-แพคเกจ-กับ-โครงการของคุณ-ระบบนิเวศ/การกําหนดค่า-docker-for-use-with-github-packages
/แพคเกจ/ไกด์/คู่มือคอนเทนเนอร์-สําหรับ-github-แพคเกจ/การกําหนดค่า-docker-for-use-with-github-packages
/แพคเกจ/คู่มือ/การกําหนดค่า-docker-for-use-with-github-แพคเกจ
เอฟพีที	เนยใส	แก	กฟผ.
*
*
*
*
รีจิสทรี Docker
{% ifversion fpt หรือ ghec %}

รีจิสทรี Docker ของ {% data variables.product.prodname_dotcom %} (ซึ่งใช้เนมสเปซ ) ถูกแทนที่ด้วยข้อมูล {% variables.product.prodname_container_registry %} (ซึ่งใช้เนมสเปซ) ข้อมูล {% variables.product.prodname_container_registry %} มอบสิทธิประโยชน์ต่างๆ เช่น สิทธิ์แบบละเอียดและการเพิ่มประสิทธิภาพการจัดเก็บสําหรับอิมเมจ Dockerdocker.pkg.github.comhttps://ghcr.io

อิมเมจ Docker ที่จัดเก็บไว้ก่อนหน้านี้ในรีจิสทรี Docker จะถูกย้ายไปยังข้อมูล {% variables.product.prodname_container_registry %} โดยอัตโนมัติ สําหรับข้อมูลเพิ่มเติม โปรดดูที่ "การย้ายข้อมูลไปยัง {% ข้อมูล variables.product.prodname_container_registry %} จากรีจิสทรี Docker" และ "การทํางานกับข้อมูล {% variables.product.prodname_container_registry %}"

{% อื่น %}

{% data reusables.package_registry.packages-ghes-release-stage %} {% data reusables.package_registry.packages-ghae-release-stage %}

{% data reusables.package_registry.admins-can-configure-package-types %}

เกี่ยวกับการสนับสนุนของ Docker
เมื่อติดตั้งหรือเผยแพร่อิมเมจ Docker รีจิสทรี Docker ไม่สนับสนุนเลเยอร์ต่างประเทศ เช่น อิมเมจของ Windows ในขณะนี้

การรับรองความถูกต้องเป็น {% ข้อมูล variables.product.prodname_registry %}
{% data reusables.package_registry.authenticate-packages %}

{% data reusables.package_registry.authenticate-packages-github-token %}

การรับรองความถูกต้องด้วยข้อมูล {% variables.product.pat_generic %}
{% ข้อมูล reusables.package_registry.need-scopes %}

คุณสามารถรับรองความถูกต้องเป็น {% data variables.product.prodname_registry %} ด้วย Docker โดยใช้คําสั่ง logindocker

เราขอแนะนําให้คุณบันทึกข้อมูล {% variables.product.pat_generic %} ในไฟล์ในเครื่องบนคอมพิวเตอร์ของคุณ และใช้แฟล็กของ Docker ซึ่งจะอ่านโทเค็นของคุณจากไฟล์ในเครื่อง--password-stdin

{% ifversion fpt หรือ ghec %} {% ดิบ %}

$ cat ~/TOKEN.txt | docker login https://docker.pkg.github.com -u <em>USERNAME</em> --password-stdin
{% endraw %} {% endif %}

{% ifversion ghes หรือ ghae %} {% ifversion ghes %} หากอินสแตนซ์ของคุณเปิดใช้งานการแยกโดเมนย่อย: {% endif %} {% ดิบ %}

$ cat ~/TOKEN.txt | docker login docker.HOSTNAME -u USERNAME --password-stdin
{% endraw %} {% ifversion ghes %} หากอินสแตนซ์ของคุณปิดใช้งานการแยกโดเมนย่อย:

{% ดิบ %}

$ cat ~/TOKEN.txt | docker login HOSTNAME -u USERNAME --password-stdin
{% endraw %} {% endif %}

{% endif %}

เมื่อต้องการใช้คําสั่ง login ตัวอย่างนี้ ให้แทนที่ด้วย {% data variables.product.product_name %} username{% ifversion ghes หรือ ghae %} ด้วย URL สําหรับ {% data variables.location.product_location %},{% endif %} และด้วยพาธไฟล์ไปยัง {% data variables.product.pat_generic %} ของคุณสําหรับ {% data variables.product.product_name %}USERNAMEHOSTNAME~/TOKEN.txt

สําหรับข้อมูลเพิ่มเติม โปรดดูที่ "การเข้าสู่ระบบ Docker"

การเผยแพร่รูปภาพ
{% data reusables.package_registry.docker_registry_deprecation_status %}

{% หมายเหตุ %}

โน้ต: ชื่อรูปภาพต้องใช้ตัวอักษรพิมพ์เล็กเท่านั้น

{% อ้างอิงท้ายเรื่อง %}

{% data variables.product.prodname_registry %} รองรับอิมเมจ Docker ระดับบนสุดหลายภาพต่อที่เก็บ ที่เก็บสามารถมีแท็กรูปภาพจํานวนเท่าใดก็ได้ คุณอาจพบการเผยแพร่บริการที่ลดลงหรือติดตั้งอิมเมจ Docker ที่มีขนาดใหญ่กว่า 10GB เลเยอร์จะถูกจํากัดไว้ที่ 5GB แต่ละเลเยอร์ สําหรับข้อมูลเพิ่มเติม โปรดดู "แท็ก Docker" ในเอกสารประกอบของ Docker

{% ข้อมูล reusables.package_registry.viewing-packages %}

กําหนดชื่อภาพและ ID สําหรับภาพ docker ของคุณโดยใช้docker images
$ docker images
> <&nbsp>
> REPOSITORY        TAG        IMAGE ID       CREATED      SIZE
> IMAGE_NAME        VERSION    IMAGE_ID       4 weeks ago  1.11MB
ใช้รหัสอิมเมจ Docker แท็กอิมเมจ docker แทนที่ OWNER ด้วยชื่อของผู้ใช้หรือบัญชีองค์กรที่เป็นเจ้าของที่เก็บ ที่เก็บที่มีชื่อของที่เก็บที่มีโครงการของคุณ IMAGE_NAME ด้วยชื่อของแพ็คเกจหรืออิมเมจ{% ifversion ghes หรือ ghae %} HOSTNAME ที่มีชื่อโฮสต์ของ {% data variables.location.product_location %},{% endif %} และ VERSION ด้วยเวอร์ชันแพ็คเกจในเวลาที่สร้าง {% ifversion fpt หรือ ghec %}
$ docker tag IMAGE_ID docker.pkg.github.com/OWNER/REPOSITORY/IMAGE_NAME:VERSION
{% อื่น %} {% ifversion ghes %} หากอินสแตนซ์ของคุณเปิดใช้งานการแยกโดเมนย่อย: {% endif %}

$ docker tag IMAGE_ID docker.HOSTNAME/OWNER/REPOSITORY/IMAGE_NAME:VERSION
{% ifversion ghes %} หากอินสแตนซ์ของคุณปิดใช้งานการแยกโดเมนย่อย:

$ docker tag IMAGE_ID HOSTNAME/OWNER/REPOSITORY/IMAGE_NAME:VERSION
{% endif %} {% endif %} 3. หากคุณยังไม่ได้สร้างอิมเมจ docker สําหรับแพ็คเกจให้สร้างรูปภาพแทนที่ OWNER ด้วยชื่อผู้ใช้หรือบัญชีองค์กรที่เป็นเจ้าของที่เก็บที่เก็บที่มีชื่อของที่เก็บที่มีโครงการของคุณIMAGE_NAMEด้วยชื่อของแพ็คเกจหรือรูปภาพ VERSION พร้อมเวอร์ชันแพ็คเกจในเวลาที่สร้าง {% ifversion ghes หรือ ghae %} HOSTNAME ที่มีชื่อโฮสต์ของ {% data variables.location.product_location %},{% endif %} และ PATH ไปยังอิมเมจหากไม่ได้อยู่ในไดเร็กทอรีการทํางานปัจจุบัน {% ifversion fpt หรือ ghec %}

$ docker build -t docker.pkg.github.com/OWNER/REPOSITORY/IMAGE_NAME:VERSION PATH
{% อื่น %} {% ifversion ghes %} หากอินสแตนซ์ของคุณเปิดใช้งานการแยกโดเมนย่อย: {% endif %}

$ docker build -t docker.HOSTNAME/OWNER/REPOSITORY/IMAGE_NAME:VERSION PATH
{% ifversion ghes %} หากอินสแตนซ์ของคุณปิดใช้งานการแยกโดเมนย่อย:

$ docker build -t HOSTNAME/OWNER/REPOSITORY/IMAGE_NAME:VERSION PATH
{% endif %} {% endif %} 4. เผยแพร่รูปภาพไปยัง {% ข้อมูล variables.product.prodname_registry %} {% ifversion fpt หรือ ghec %}

$ docker push docker.pkg.github.com/OWNER/REPOSITORY/IMAGE_NAME:VERSION
{% อื่น %} {% ifversion ghes %} หากอินสแตนซ์ของคุณเปิดใช้งานการแยกโดเมนย่อย: {% endif %}

$ docker push docker.HOSTNAME/OWNER/REPOSITORY/IMAGE_NAME:VERSION
{% ifversion ghes %} หากอินสแตนซ์ของคุณปิดใช้งานการแยกโดเมนย่อย:

$ docker push HOSTNAME/OWNER/REPOSITORY/IMAGE_NAME:VERSION
{% endif %} {% endif %} {% หมายเหตุ %}

โน้ต: คุณต้องผลักดันภาพของคุณโดยใช้และไม่ใช้IMAGE_NAME:VERSIONIMAGE_NAME:SHA

{% อ้างอิงท้ายเรื่อง %}

ตัวอย่างการเผยแพร่รูป Docker
{% ifversion ghes %} ตัวอย่างเหล่านี้ถือว่าอินสแตนซ์ของคุณเปิดใช้งานการแยกโดเมนย่อยแล้ว {% endif %}

คุณสามารถเผยแพร่เวอร์ชัน 1.0 ของรูปภาพไปยังที่เก็บโดยใช้รหัสรูปภาพmonalisaoctocat/octo-app

{% ifversion fpt หรือ ghec %}

$ docker images

> REPOSITORY           TAG      IMAGE ID      CREATED      SIZE
> monalisa             1.0      c75bebcdd211  4 weeks ago  1.11MB

# Tag the image with <em>OWNER/REPO/IMAGE_NAME</em>
$ docker tag c75bebcdd211 docker.pkg.github.com/octocat/octo-app/monalisa:1.0

# Push the image to {% data variables.product.prodname_registry %}
$ docker push docker.pkg.github.com/octocat/octo-app/monalisa:1.0
{% อื่น %}

$ docker images

> REPOSITORY           TAG      IMAGE ID      CREATED      SIZE
> monalisa             1.0      c75bebcdd211  4 weeks ago  1.11MB

# Tag the image with <em>OWNER/REPO/IMAGE_NAME</em>
$ docker tag c75bebcdd211 docker.HOSTNAME/octocat/octo-app/monalisa:1.0

# Push the image to {% data variables.product.prodname_registry %}
$ docker push docker.HOSTNAME/octocat/octo-app/monalisa:1.0
{% endif %}

You can publish a new Docker image for the first time and name it .monalisa

{% ifversion fpt or ghec %}

# Build the image with docker.pkg.github.com/<em>OWNER/REPOSITORY/IMAGE_NAME:VERSION</em>
# Assumes Dockerfile resides in the current working directory (.)
$ docker build -t docker.pkg.github.com/octocat/octo-app/monalisa:1.0 .

# Push the image to {% data variables.product.prodname_registry %}
$ docker push docker.pkg.github.com/octocat/octo-app/monalisa:1.0
{% else %}

# Build the image with docker.<em>HOSTNAME/OWNER/REPOSITORY/IMAGE_NAME:VERSION</em>
# Assumes Dockerfile resides in the current working directory (.)
$ docker build -t docker.HOSTNAME/octocat/octo-app/monalisa:1.0 .

# Push the image to {% data variables.product.prodname_registry %}
$ docker push docker.HOSTNAME/octocat/octo-app/monalisa:1.0
{% endif %}

Downloading an image
{% data reusables.package_registry.docker_registry_deprecation_status %}

คุณสามารถใช้คําสั่งเพื่อติดตั้งอิมเมจ docker จาก {% data variables.product.prodname_registry %} แทนที่ OWNER ด้วยชื่อของผู้ใช้หรือบัญชีองค์กรที่เป็นเจ้าของที่เก็บ ที่เก็บด้วยชื่อของที่เก็บที่มีโครงการของคุณ IMAGE_NAME ด้วยชื่อของแพคเกจหรืออิมเมจ{% ifversion ghes หรือ ghae %} HOSTNAME ที่มีชื่อโฮสต์ของ {% data variables.location.product_location %}, {% endif %} และTAG_NAMEด้วยแท็กสําหรับรูปภาพที่คุณต้องการติดตั้งdocker pull

{% ifversion fpt หรือ ghec %}

$ docker pull docker.pkg.github.com/OWNER/REPOSITORY/IMAGE_NAME:TAG_NAME
{% อื่น %}

{% ifversion ghes %} หากอินสแตนซ์ของคุณเปิดใช้งานการแยกโดเมนย่อย: {% endif %}

$ docker pull docker.HOSTNAME/OWNER/REPOSITORY/IMAGE_NAME:TAG_NAME
{% ifversion ghes %} หากอินสแตนซ์ของคุณปิดใช้งานการแยกโดเมนย่อย:

$ docker pull HOSTNAME/OWNER/REPOSITORY/IMAGE_NAME:TAG_NAME
{% endif %} {% endif %}

{% หมายเหตุ %}

โน้ต: คุณต้องดึงภาพโดยใช้และไม่ใช้IMAGE_NAME:VERSIONIMAGE_NAME:SHA

{% อ้างอิงท้ายเรื่อง %}

อ่านเพิ่มเติม
"การลบและการคืนค่าแพคเกจ"
{% endif %}
กล้า	** ** หรือ __ __	Command+B (Mac) หรือ + (วินโดวส์/ลินุกซ์)CtrlB	**This is bold text**	นี่คือข้อความตัวหนา
ตัวเอียง	* * หรือ _ _	Command+I (Mac) หรือ + (วินโดวส์/ลินุกซ์)CtrlI	*This text is italicized*	ข้อความนี้เป็นตัวเอียง
ขีดฆ่า	~~ ~~		~~This was mistaken text~~	นี่เป็นข้อความที่ผิดพลาด
ตัวเอียงตัวหนาและซ้อนกัน	** ** และ _ _		**This text is _extremely_ important**	ข้อความนี้มีความสําคัญอย่างยิ่ง
ตัวหนาและตัวเอียงทั้งหมด	*** ***		***All this text is important***	ข้อความทั้งหมดนี้มีความสําคัญ
ตัวห้อย	<sub> </sub>		<sub>This is a subscript text</sub>	นี่คือข้อความตัวห้อย
ตัวยก	<sup> </sup>		<sup>This is a superscript text</sup>	นี่คือข้อความตัวยก
อ้างข้อความ
คุณสามารถอ้างอิงข้อความด้วย>

Text that is not a quote

> Text that is a quote
ข้อความที่ยกมาแสดงผล

ปลาย: เมื่อดูการสนทนา คุณสามารถอ้างอิงข้อความในความคิดเห็นได้โดยอัตโนมัติโดยการไฮไลท์ข้อความ แล้วพิมพ์ คุณสามารถอ้างอิงความคิดเห็นทั้งหมดได้โดยคลิกจากนั้นอ้างการตอบกลับ สําหรับข้อมูลเพิ่มเติมเกี่ยวกับแป้นพิมพ์ลัด ให้ดูที่ "แป้นพิมพ์ลัด"R

รหัสอ้างอิง
คุณสามารถเรียกรหัสหรือคําสั่งภายในประโยคที่มี backticks เดียว ข้อความภายใน backticks จะไม่ถูกจัดรูปแบบ คุณยังสามารถกดแป้นพิมพ์ลัด + (Mac) หรือ + (Windows/Linux) เพื่อแทรก backticks สําหรับบล็อกรหัสภายในบรรทัดของ MarkdownCommandECtrlE

Use `git status` to list all new or modified files that haven't yet been committed.
Rendered inline code block

To format code or text into its own distinct block, use triple backticks.

Some basic Git commands are:
```
git status
git add
git commit
```
Rendered code block

For more information, see "Creating and highlighting code blocks."

If you are frequently editing code snippets and tables, you may benefit from enabling a fixed-width font in all comment fields on GitHub. For more information, see "Enabling fixed-width fonts in the editor."

Supported color models
In issues, pull requests, and discussions, you can call out colors within a sentence by using backticks. A supported color model within backticks will display a visualization of the color.

The background color should be `#ffffff` for light mode and `#0d1117` for dark mode.
Rendered supported color model.

Here are the currently supported color models.

Color	Syntax	Example	Output
HEX	`#RRGGBB`	`#0969DA`	Rendered supported color model in HEX format.
RGB	`rgb(R,G,B)`	`rgb(9, 105, 218)`	Rendered supported color model in RGB format.
HSL	`hsl(H,S,L)`	`hsl(212, 92%, 45%)`	Rendered supported color model in HSL format.
Notes:

A supported color model cannot have any leading or trailing spaces within the backticks.
The visualization of the color is only supported in issues, pull requests, and discussions.
Links
You can create an inline link by wrapping link text in brackets , and then wrapping the URL in parentheses . You can also use the keyboard shortcut + to create a link. When you have text selected, you can paste a URL from your clipboard to automatically create a link from the selection.[ ]( )CommandK

You can also create a Markdown hyperlink by highlighting the text and using the keyboard shortcut +. If you'd like to replace the text with the link, use the keyboard shortcut ++.CommandVCommandShiftV

This site was built using [GitHub Pages](https://pages.github.com/).

Rendered link

Tip: GitHub automatically creates links when valid URLs are written in a comment. For more information, see "Autolinked references and URLs."

Section links
You can link directly to a section in a rendered file by hovering over the section heading to expose the link:

Section link within the README file for the github/scientist repository

Relative links
You can define relative links and image paths in your rendered files to help readers navigate to other files in your repository.

A relative link is a link that is relative to the current file. For example, if you have a README file in root of your repository, and you have another file in docs/CONTRIBUTING.md, the relative link to CONTRIBUTING.md in your README might look like this:

[Contribution guidelines for this project](docs/CONTRIBUTING.md)
GitHub will automatically transform your relative link or image path based on whatever branch you're currently on, so that the link or path always works. The path of the link will be relative to the current file. Links starting with will be relative to the repository root. You can use all relative link operands, such as and ././../

Relative links are easier for users who clone your repository. Absolute links may not work in clones of your repository - we recommend using relative links to refer to other files within your repository.

Images
You can display an image by adding and wrapping the alt text in . Then wrap the link for the image in parentheses .![ ]()

![This is an image](https://myoctocat.com/assets/images/base-octocat.svg)

Rendered Image

GitHub supports embedding images into your issues, pull requests, discussions, comments and files. You can display an image from your repository, add a link to an online image, or upload an image. For more information, see "Uploading assets.".md

Tip: When you want to display an image which is in your repository, you should use relative links instead of absolute links.

Here are some examples for using relative links to display an image.

Context	Relative Link
In a file on the same branch.md	/assets/images/electrocat.png
In a file on another branch.md	/../main/assets/images/electrocat.png
In issues, pull requests and comments of the repository	../blob/main/assets/images/electrocat.png?raw=true
In a file in another repository.md	/../../../../github/docs/blob/main/assets/images/electrocat.png
In issues, pull requests and comments of another repository	../../../github/docs/blob/main/assets/images/electrocat.png?raw=true
Note: The last two relative links in the table above will work for images in a private repository only if the viewer has at least read access to the private repository which contains these images.

For more information, see "Relative Links."

Specifying the theme an image is shown to
You can specify the theme an image is displayed for in Markdown by using the HTML element in combination with the media feature. We distinguish between light and dark color modes, so there are two options available. You can use these options to display images optimized for dark or light backgrounds. This is particularly helpful for transparent PNG images.<picture>prefers-color-scheme

For example, the following code displays a sun image for light themes and a moon for dark themes:

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://user-images.githubusercontent.com/25423296/163456776-7f95b81a-f1ed-45f7-b7ab-8fa810d529fa.png">
  <source media="(prefers-color-scheme: light)" srcset="https://user-images.githubusercontent.com/25423296/163456779-a8556205-d0a5-45e2-ac17-42d089e3c3f8.png">
  <img alt="Shows an illustrated sun in light mode and a moon with stars in dark mode." src="https://user-images.githubusercontent.com/25423296/163456779-a8556205-d0a5-45e2-ac17-42d089e3c3f8.png">
</picture>
The old method of specifying images based on the theme, by using a fragment appended to the URL ( or ), is deprecated and will be removed in favor of the new method described above.#gh-dark-mode-only#gh-light-mode-only

Lists
You can make an unordered list by preceding one or more lines of text with , , or .-*+

- George Washington
* John Adams
+ Thomas Jefferson
Rendered unordered list

To order your list, precede each line with a number.

1. James Madison
2. James Monroe
3. John Quincy Adams
Rendered ordered list

Nested Lists
You can create a nested list by indenting one or more list items below another item.

To create a nested list using the web editor on GitHub or a text editor that uses a monospaced font, like Visual Studio Code, you can align your list visually. Type space characters in front of your nested list item, until the list marker character ( or ) lies directly below the first character of the text in the item above it.-*

1. First list item
   - First nested list item
     - Second nested list item
Note: In the web-based editor, you can indent or dedent one or more lines of text by first highlighting the desired lines and then using or + respectively.TabShiftTab

Nested list with alignment highlighted

List with two levels of nested items

To create a nested list in the comment editor on GitHub, which doesn't use a monospaced font, you can look at the list item immediately above the nested list and count the number of characters that appear before the content of the item. Then type that number of space characters in front of the nested list item.

In this example, you could add a nested list item under the list item by indenting the nested list item a minimum of five spaces, since there are five characters () before .100. First list item100. First list item

100. First list item
     - First nested list item
List with a nested list item

You can create multiple levels of nested lists using the same method. For example, because the first nested list item has seven characters () before the nested list content , you would need to indent the second nested list item by seven spaces.␣␣␣␣␣-␣First nested list item

100. First list item
     - First nested list item
       - Second nested list item
List with two levels of nested items

For more examples, see the GitHub Flavored Markdown Spec.

Task lists
To create a task list, preface list items with a hyphen and space followed by . To mark a task as complete, use .[ ][x]

- [x] #739
- [ ] https://github.com/octo-org/octo-repo/issues/740
- [ ] Add delight to the experience when all tasks are complete :tada:
Rendered task list

If a task list item description begins with a parenthesis, you'll need to escape it with :\

- [ ] \(Optional) Open a followup issue

For more information, see "About task lists."

Mentioning people and teams
You can mention a person or team on GitHub by typing plus their username or team name. This will trigger a notification and bring their attention to the conversation. People will also receive a notification if you edit a comment to mention their username or team name. For more information about notifications, see "About notifications."@

Note: A person will only be notified about a mention if the person has read access to the repository and, if the repository is owned by an organization, the person is a member of the organization.

@github/support What do you think about these updates?

Rendered @mention

When you mention a parent team, members of its child teams also receive notifications, simplifying communication with multiple groups of people. For more information, see "About teams."

Typing an symbol will bring up a list of people or teams on a project. The list filters as you type, so once you find the name of the person or team you are looking for, you can use the arrow keys to select it and press either tab or enter to complete the name. For teams, enter the @organization/team-name and all members of that team will get subscribed to the conversation.@

The autocomplete results are restricted to repository collaborators and any other participants on the thread.

Referencing issues and pull requests
You can bring up a list of suggested issues and pull requests within the repository by typing . Type the issue or pull request number or title to filter the list, and then press either tab or enter to complete the highlighted result.#

For more information, see "Autolinked references and URLs."

Referencing external resources
If custom autolink references are configured for a repository, then references to external resources, like a JIRA issue or Zendesk ticket, convert into shortened links. To know which autolinks are available in your repository, contact someone with admin permissions to the repository. For more information, see "Configuring autolinks to reference external resources."

Uploading assets
You can upload assets like images by dragging and dropping, selecting from a file browser, or pasting. You can upload assets to issues, pull requests, comments, and files in your repository..md

Using emoji
You can add emoji to your writing by typing .:EMOJICODE:

@octocat :+1: This PR looks great - it's ready to merge! :shipit:

Rendered emoji

Typing will bring up a list of suggested emoji. The list will filter as you type, so once you find the emoji you're looking for, press Tab or Enter to complete the highlighted result.:

For a full list of available emoji and codes, check out the Emoji-Cheat-Sheet.

Paragraphs
You can create a new paragraph by leaving a blank line between lines of text.

Footnotes
You can add footnotes to your content by using this bracket syntax:

Here is a simple footnote[^1].

A footnote can also have multiple lines[^2].  

You can also use words, to fit your writing style more closely[^note].

[^1]: My reference.
[^2]: Every new line should be prefixed with 2 spaces.  
  This allows you to have a footnote with multiple lines.
[^note]:
    Named footnotes will still render with numbers instead of the text but allow easier identification and linking.  
    This footnote also has been made with a different syntax using 4 spaces for new lines.
The footnote will render like this:

Rendered footnote

Note: The position of a footnote in your Markdown does not influence where the footnote will be rendered. You can write a footnote right after your reference to the footnote, and the footnote will still render at the bottom of the Markdown.

Footnotes are not supported in wikis.

Hiding content with comments
You can tell GitHub to hide content from the rendered Markdown by placing the content in an HTML comment.

<!-- This content will not appear in the rendered Markdown -->
Ignoring Markdown formatting
You can tell GitHub to ignore (or escape) Markdown formatting by using before the Markdown character.\

Let's rename \*our-new-project\* to \*our-old-project\*.

Rendered escaped character

For more information, see Daring Fireball's "Markdown Syntax."

Disabling Markdown rendering
When viewing a Markdown file, you can click at the top of the file to disable Markdown rendering and view the file's source instead.

Display Markdown as source

Disabling Markdown rendering enables you to use source view features, such as line linking, which is not possible when viewing rendered Markdown files.

Further reading
GitHub Flavored Markdown Spec
"About writing and formatting on GitHub"
"Working with advanced formatting"
"เริ่มต้นใช้งานด่วนสําหรับการเขียนบน GitHub"
เอกสารนี้ช่วยคุณได้หรือไม่?

นโยบายความเป็นส่วนตัว
ช่วยเราทําให้เอกสารเหล่านี้ยอดเยี่ยม!
เอกสาร GitHub ทั้งหมดเป็นโอเพ่นซอร์ส เห็นสิ่งผิดปกติหรือไม่ชัดเจน? ส่งคําขอดึงข้อมูล

หรือดูวิธีมีส่วนร่วม
หากยังต้องการความช่วยเหลือ
ถามชุมชน GitHub
ติดต่อฝ่ายสนับสนุน
© 2022 GitHub, Inc.
เงื่อนไข
ความเป็นส่วนตัว
ความปลอดภัย
สถานะ
วิธีใช้
ติดต่อ GitHub
ราคา
API สําหรับนักพัฒนา
การอบรม
บล็อก
ประมาณ​00399
- name: Setup .NET Core SDK
  uses: actions/setup-dotnet@v3.0.3

