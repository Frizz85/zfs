<html>

<head>
<meta http-equiv=Content-Type content="text/html; charset=windows-1251">
<meta name=Generator content="Microsoft Word 15 (filtered)">
<style>
<!--
 /* Font Definitions */
 @font-face
	{font-family:"Cambria Math";
	panose-1:2 4 5 3 5 4 6 3 2 4;}
@font-face
	{font-family:Calibri;
	panose-1:2 15 5 2 2 2 4 3 2 4;}
@font-face
	{font-family:"Segoe UI";
	panose-1:2 11 5 2 4 2 4 2 2 3;}
@font-face
	{font-family:Consolas;
	panose-1:2 11 6 9 2 2 4 3 2 4;}
 /* Style Definitions */
 p.MsoNormal, li.MsoNormal, div.MsoNormal
	{margin-top:0cm;
	margin-right:0cm;
	margin-bottom:8.0pt;
	margin-left:0cm;
	line-height:107%;
	font-size:11.0pt;
	font-family:"Calibri",sans-serif;}
h3
	{mso-style-link:"��������� 3 ����";
	margin-right:0cm;
	margin-left:0cm;
	font-size:13.5pt;
	font-family:"Times New Roman",serif;
	font-weight:bold;}
p
	{margin-right:0cm;
	margin-left:0cm;
	font-size:12.0pt;
	font-family:"Times New Roman",serif;}
code
	{font-family:"Courier New";}
pre
	{mso-style-link:"����������� HTML ����";
	margin:0cm;
	font-size:10.0pt;
	font-family:"Courier New";}
span.HTML
	{mso-style-name:"����������� HTML ����";
	mso-style-link:"����������� HTML";
	font-family:"Courier New";}
span.3
	{mso-style-name:"��������� 3 ����";
	mso-style-link:"��������� 3";
	font-family:"Times New Roman",serif;
	font-weight:bold;}
.MsoChpDefault
	{font-family:"Calibri",sans-serif;}
.MsoPapDefault
	{margin-bottom:8.0pt;
	line-height:107%;}
@page WordSection1
	{size:595.3pt 841.9pt;
	margin:2.0cm 42.5pt 2.0cm 3.0cm;}
div.WordSection1
	{page:WordSection1;}
-->
</style>

</head>

<body lang=RU style='word-wrap:break-word'>

<div class=WordSection1>

<p class=MsoNormal style='margin-top:18.0pt;margin-right:0cm;margin-bottom:
12.0pt;margin-left:0cm;line-height:normal;background:white'><b><span
style='font-size:15.0pt;font-family:"Segoe UI",sans-serif;color:#24292F'>1.
����������� ��������� � ��������� �������</span></b></p>

<p class=MsoNormal style='margin-bottom:12.0pt;line-height:normal;background:
white'><span style='font-size:12.0pt;font-family:"Segoe UI",sans-serif;
color:#24292F'>������ ���� ������, ������� ���� �� ����������� ������:</span></p>

<p class=MsoNormal style='margin-bottom:0cm;line-height:normal'><span
style='font-size:10.0pt;font-family:Consolas;color:#24292F'>lsblk</span></p>

<p class=MsoNormal>&nbsp;</p>

<p class=MsoNormal><img width=367 height=184 id="������� 1"
src="zfs.files/image001.png"></p>

<p class=MsoNormal>&nbsp;</p>

<p style='margin-top:0cm;margin-right:0cm;margin-bottom:12.0pt;margin-left:
0cm;background:white'><span style='font-family:"Segoe UI",sans-serif;
color:#24292F'>�������� ����� � ������ RAID 1:</span></p>

<pre style='background:white'><code><span lang=EN-US style='font-family:Consolas;
color:#24292F'>zpool create otus1 mirror /dev/sdb /dev/sdc</span></code></pre><pre
style='background:white'><code><span lang=EN-US style='font-family:Consolas;
color:#24292F'>zpool create otus2 mirror /dev/sdd /dev/sde</span></code></pre><pre
style='background:white'><code><span lang=EN-US style='font-family:Consolas;
color:#24292F'>zpool create otus3 mirror /dev/sdf /dev/sdg</span></code></pre><pre
style='background:white'><code><span lang=EN-US style='font-family:Consolas;
color:#24292F'>zpool create otus4 mirror /dev/sdh /dev/sdi</span></code></pre>

<p class=MsoNormal><span lang=EN-US>&nbsp;</span></p>

<p style='margin-top:0cm;margin-right:0cm;margin-bottom:12.0pt;margin-left:
0cm;background:white'><span style='font-family:"Segoe UI",sans-serif;
color:#24292F'>��������� ����:</span></p>

<pre style='background:white'><code><span style='font-family:Consolas;
color:#24292F'>zpool list</span></code></pre>

<p class=MsoNormal><span lang=EN-US>&nbsp;</span></p>

<p class=MsoNormal><img width=623 height=101 id="������� 2"
src="zfs.files/image002.jpg"
alt="����������� �������� ��� �����, ����������, �������, ������&#10;&#10;������������� ��������� ��������"></p>

<p class=MsoNormal>zpool status</p>

<p class=MsoNormal><img width=496 height=798 id="������� 3"
src="zfs.files/image003.png"></p>

<p class=MsoNormal>&nbsp;</p>

<p class=MsoNormal>&nbsp;</p>

<p class=MsoNormal>&nbsp;</p>

<p class=MsoNormal>&nbsp;</p>

<p class=MsoNormal>&nbsp;</p>

<p class=MsoNormal>������� ������ ��������� ������ � ������ �������� �������:</p>

<p class=MsoNormal><span lang=EN-US>&#9679; �������� lzjb: zfs set
compression=lzjb otus1</span></p>

<p class=MsoNormal><span lang=EN-US>&#9679; �������� lz4: zfs set
compression=lz4 otus2</span></p>

<p class=MsoNormal><span lang=EN-US>&#9679; �������� gzip: zfs set
compression=gzip-9 otus3</span></p>

<p class=MsoNormal><span lang=EN-US>&#9679; �������� zle: zfs set
compression=zle otus4</span></p>

<p class=MsoNormal></p>

<p class=MsoNormal><span style='font-family:"Segoe UI",sans-serif;color:#24292F;
background:white'>������</span><span style='font-family:"Segoe UI",sans-serif;
color:#24292F;background:white'> </span><span style='font-family:"Segoe UI",sans-serif;
color:#24292F;background:white'>������</span><span style='font-family:"Segoe UI",sans-serif;
color:#24292F;background:white'> </span><span style='font-family:"Segoe UI",sans-serif;
color:#24292F;background:white'>��������</span><span style='font-family:"Segoe UI",sans-serif;
color:#24292F;background:white'> </span><span style='font-family:"Segoe UI",sans-serif;
color:#24292F;background:white'>������</span><span lang=EN-US style='font-family:
"Segoe UI",sans-serif;color:#24292F;background:white'>:</span></p>

<p class=MsoNormal><span lang=EN-US>zfs get all | grep compression</span></p>

<p class=MsoNormal><img width=478 height=103 id="������� 4"
src="zfs.files/image004.png"
alt="����������� �������� ��� �����, ����������, �������, ������&#10;&#10;������������� ��������� ��������"></p>

<p class=MsoNormal><span style='font-family:"Segoe UI",sans-serif;color:#24292F;
background:white'>���������� ������ �� ��� ����</span></p>

<p class=MsoNormal><span lang=EN-US>for i in {1..4}; do wget -P /otus$i
https://gutenberg.org/cache/epub/2600/pg2600.converter.log; done</span></p>

<p class=MsoNormal>ls -l /otus*</p>

<p class=MsoNormal><img width=624 height=263 id="������� 5"
src="zfs.files/image005.jpg"
alt="����������� �������� ��� �����&#10;&#10;������������� ��������� ��������"></p>

<p class=MsoNormal>&nbsp;</p>

<p class=MsoNormal>&nbsp;</p>

<p class=MsoNormal>&nbsp;</p>

<p class=MsoNormal>&nbsp;</p>

<p class=MsoNormal>&nbsp;</p>

<p class=MsoNormal>&nbsp;</p>

<p class=MsoNormal>&nbsp;</p>

<p class=MsoNormal>&nbsp;</p>

<p class=MsoNormal>��������, ��� ���� ��� ������ �� ��� ����:</p>

<p class=MsoNormal>ls -l /otus*</p>

<p class=MsoNormal><img width=608 height=261 id="������� 6"
src="zfs.files/image006.png"
alt="����������� �������� ��� �����&#10;&#10;������������� ��������� ��������"></p>

<p class=MsoNormal>��������, ������� ����� �������� ���� � ��� �� ���� � ������
����� � �������� ������� ������ ������:</p>

<p class=MsoNormal>zfs list</p>

<p class=MsoNormal><img width=426 height=112 id="������� 7"
src="zfs.files/image007.png"
alt="����������� �������� ��� �����&#10;&#10;������������� ��������� ��������"></p>

<p class=MsoNormal>&nbsp;</p>

<p class=MsoNormal><span lang=EN-US>zfs get all | grep compressratio | grep -v
ref</span></p>

<p class=MsoNormal><img width=507 height=95 id="������� 8"
src="zfs.files/image008.png"
alt="����������� �������� ��� �����&#10;&#10;������������� ��������� ��������"></p>

<p class=MsoNormal style='margin-top:18.0pt;margin-right:0cm;margin-bottom:
12.0pt;margin-left:0cm;line-height:normal;background:white'><b><span
style='font-size:12.0pt;font-family:"Segoe UI",sans-serif;color:#24292F'>�����</span></b></p>

<p class=MsoNormal style='margin-bottom:12.0pt;line-height:normal;background:
white'><i><span style='font-size:12.0pt;font-family:"Segoe UI",sans-serif;
color:#24292F'>�������� gzip-9 ����� ����������� �� ������.</span></i></p>

<p class=MsoNormal>&nbsp;</p>

<p class=MsoNormal>&nbsp;</p>

<p class=MsoNormal>&nbsp;</p>

<p class=MsoNormal>&nbsp;</p>

<p class=MsoNormal>&nbsp;</p>

<p class=MsoNormal>&nbsp;</p>

<p class=MsoNormal style='margin-top:18.0pt;margin-right:0cm;margin-bottom:
12.0pt;margin-left:0cm;line-height:normal;background:white'><b><span
style='font-size:18.0pt;font-family:"Segoe UI",sans-serif;color:#24292F'>2.
����������� �������� ����</span></b></p>

<p class=MsoNormal>&nbsp;</p>

<p class=MsoNormal>��������� ����� � �������� �������:</p>

<pre><code><span lang=EN-US style='font-family:Consolas;color:#24292F'>wget -O archive.tar.gz --no-check-certificate 'https://drive.google.com/u/0/uc?id=1KRBNW33QWqbvbVHa3hLJivOAt60yukkg&amp;e</span></code></pre><pre><code><span
lang=EN-US style='font-family:Consolas;color:#24292F'>xport=download'</span></code></pre><pre><code><span
lang=EN-US style='font-family:Consolas;color:#24292F'>tar -xzvf archive.tar.gz</span></code></pre><pre><span
lang=EN-US style='font-family:Consolas;color:#24292F'>&nbsp;</span></pre><pre><img
width=623 height=157 id="������� 9" src="zfs.files/image009.jpg"
alt="����������� �������� ��� �����, ����������, ������ ������&#10;&#10;������������� ��������� ��������"></pre><pre><span
lang=EN-US style='font-family:Consolas;color:#24292F'>&nbsp;</span></pre><pre>&nbsp;</pre><pre>������������� ���:</pre><pre><code><span
lang=EN-US style='font-family:Consolas;color:#24292F'>tar -xzvf archive.tar.gz</span></code></pre><pre><code><span
lang=EN-US style='font-family:Consolas;color:#24292F'>&nbsp;</span></code></pre><pre><img
width=366 height=116 id="������� 10" src="zfs.files/image010.png"
alt="����������� �������� ��� �����&#10;&#10;������������� ��������� ��������"></pre><pre><span
lang=EN-US style='font-family:Consolas;color:#24292F'>&nbsp;</span></pre><pre>��������, �������� �� ������������� ������ ������� � ���:</pre><pre>zpool import -d zpoolexport/</pre><pre><span
style='font-family:Consolas;color:#24292F'>&nbsp;</span></pre><pre><img
width=622 height=191 id="������� 11" src="zfs.files/image011.png"
alt="����������� �������� ��� �����&#10;&#10;������������� ��������� ��������"></pre><pre><span
lang=EN-US style='font-family:Consolas;color:#24292F'>&nbsp;</span></pre><pre><span
lang=EN-US style='font-family:Consolas;color:#24292F'>&nbsp;</span></pre><pre><span
lang=EN-US style='font-family:Consolas;color:#24292F'>&nbsp;</span></pre><pre><span
lang=EN-US style='font-family:Consolas;color:#24292F'>&nbsp;</span></pre><pre><span
lang=EN-US style='font-family:Consolas;color:#24292F'>&nbsp;</span></pre><pre><span
lang=EN-US style='font-family:Consolas;color:#24292F'>&nbsp;</span></pre><pre><span
lang=EN-US style='font-family:Consolas;color:#24292F'>&nbsp;</span></pre><pre><span
lang=EN-US style='font-family:Consolas;color:#24292F'>&nbsp;</span></pre><pre><span
lang=EN-US style='font-family:Consolas;color:#24292F'>&nbsp;</span></pre><pre><span
lang=EN-US style='font-family:Consolas;color:#24292F'>&nbsp;</span></pre><pre><span
lang=EN-US style='font-family:Consolas;color:#24292F'>&nbsp;</span></pre><pre>������ ����� ���������� ��� ��� ����, ��� raid � ��� ������. ������� ������ ������� ���� � ��� � ��:</pre><pre><span
style='font-family:Consolas;color:#24292F'>&nbsp;</span></pre><pre><img
width=538 height=176 id="������� 12" src="zfs.files/image012.png"
alt="����������� �������� ��� �����&#10;&#10;������������� ��������� ��������"></pre><pre><span
lang=EN-US style='font-family:Consolas;color:#24292F'>&nbsp;</span></pre><pre><span
style='font-family:"Segoe UI",sans-serif;color:#24292F;background:white'>��������� ����:</span></pre><pre><code><span
lang=EN-US style='font-family:Consolas;color:#24292F'>&nbsp;</span></code></pre><pre><code><span
lang=EN-US style='font-family:Consolas;color:#24292F'>zfs get available otus;</span></code></pre><pre><code><span
lang=EN-US style='font-family:Consolas;color:#24292F'>zfs get recordsize otus;</span></code></pre><pre><code><span
lang=EN-US style='font-family:Consolas;color:#24292F'>zfs get compression otus;</span></code></pre><pre><code><span
lang=EN-US style='font-family:Consolas;color:#24292F'>zfs get checksum otus</span></code></pre><pre><span
lang=EN-US style='font-family:Consolas;color:#24292F'>&nbsp;</span></pre>

<h3 style='margin-top:18.0pt;margin-right:0cm;margin-bottom:12.0pt;margin-left:
0cm;background:white'><span style='font-size:15.0pt;font-family:"Segoe UI",sans-serif;
color:#24292F'>3. ������ �� ���������, ����� ��������� �� �������������</span></h3>

<pre><span lang=EN-US style='font-family:Consolas;color:#24292F'>&nbsp;</span></pre><pre><span
style='font-family:"Segoe UI",sans-serif;color:#24292F;background:white'>���������� �����, ���������� � �������:</span></pre><pre><span
style='font-family:"Segoe UI",sans-serif;color:#24292F;background:white'>&nbsp;</span></pre><pre><code><span
lang=EN-US style='font-family:Consolas;color:#24292F'>wget -O otus_task2.file --no-check-certificate 'https://drive.google.com/u/0/uc?id=1gH8gCL9y7Nd5Ti3IRmplZPF1XjzxeRAG&amp;e</span></code></pre><pre><code><span
style='font-family:Consolas;color:#24292F'>xport=download'</span></code></pre><pre><span
style='font-family:Consolas;color:#24292F'>&nbsp;</span></pre><pre><img
width=624 height=139 id="������� 13" src="zfs.files/image013.jpg"
alt="����������� �������� ��� �����, ������ ������, �����&#10;&#10;������������� ��������� ��������"></pre><pre><code><span
lang=EN-US style='font-family:Consolas;color:#24292F'>&nbsp;</span></code></pre><pre><span
style='font-family:"Segoe UI",sans-serif;color:#24292F;background:white'>����������� �������� ������� �� ��������:</span></pre><pre><code><span
lang=EN-US style='font-family:Consolas;color:#24292F'>zfs receive otus/test@today &lt; otus_task2.file</span></code></pre><pre><span
lang=EN-US style='font-family:Consolas;color:#24292F'>&nbsp;</span></pre><pre><span
lang=EN-US style='font-family:Consolas;color:#24292F'>&nbsp;</span></pre><pre><span
style='font-family:"Segoe UI",sans-serif;color:#24292F;background:white'>�����, ���� � �������� /otus/test ���� � ������ �secret_message�:</span></pre><pre><code><span
lang=EN-US style='font-family:Consolas;color:#24292F'>find /otus/test -name &quot;secret_message&quot;</span></code></pre><pre><span
lang=EN-US style='font-family:Consolas;color:#24292F'>&nbsp;</span></pre><pre><img
width=520 height=87 id="������� 14" src="zfs.files/image014.png"
alt="����������� �������� ��� �����&#10;&#10;������������� ��������� ��������"></pre><pre><span
lang=EN-US style='font-family:Consolas;color:#24292F'>&nbsp;</span></pre><pre><code><span
lang=EN-US style='font-family:Consolas;color:#24292F'>&nbsp;</span></code></pre><pre><code><span
lang=EN-US style='font-family:Consolas;color:#24292F'>&nbsp;</span></code></pre><pre><code><span
lang=EN-US style='font-family:Consolas;color:#24292F'>&nbsp;</span></code></pre><pre><code><span
lang=EN-US style='font-family:Consolas;color:#24292F'>&nbsp;</span></code></pre><pre><code><span
lang=EN-US style='font-family:Consolas;color:#24292F'>cat /otus/test/task1/file_mess/secret_message</span></code></pre><pre><span
lang=EN-US style='font-family:Consolas;color:#24292F'>&nbsp;</span></pre><pre><img
width=491 height=62 id="������� 15" src="zfs.files/image015.png"
alt="����������� �������� ��� �����&#10;&#10;������������� ��������� ��������"></pre><pre><span
lang=EN-US style='font-family:Consolas;color:#24292F'>&nbsp;</span></pre><pre><span
lang=EN-US style='font-family:Consolas;color:#24292F'>https://github.com/sindresorhus/awesome</span></pre><pre><img
width=624 height=387 id="������� 16" src="zfs.files/image016.jpg"></pre></div>

</body>

</html>
