[![Gitter](https://badges.gitter.im/Join Chat.svg)](https://gitter.im/Wexflow/Lobby)
[![License](http://img.shields.io/badge/license-mit-blue.svg?style=flat-square)](https://github.com/aelassas/Wexflow/blob/master/LICENSE)
[![Twitter](https://img.shields.io/badge/twitter-@wexflow86-55acee.svg?style=flat-square)](https://twitter.com/wexflow86)

# Build status

|         | Status |
----------|--------|
| Travis  |[![Build Status](https://travis-ci.org/aelassas/Wexflow.svg?branch=master)](https://travis-ci.org/aelassas/Wexflow)|
| AppVeyor|[![Build Status](https://ci.appveyor.com/api/projects/status/github/aelassas/Wexflow?svg=true)](https://ci.appveyor.com/project/aelassas/wexflow)|

# Wexflow
Wexflow is an open source multithreaded workflow engine written in pure C# from scratch. Wexflow aims to make automations, workflow processes, long-running processes and interactions between systems, applications and folks easy, straitforward and clean.

![alt tag](https://aelassas.github.io/Wexflow/wa.png)

A workflow is a series of distinct steps or phases (like in the diagram above). Each step is modeled in Wexflow as a Task. Tasks can be assembled visually into workflows using XML. Assembling tasks in Design mode will be possible through Wexflow Designer. This feature is in the todo list and is comming soon.

Wexflow provides the following tasks:**

- **File system tasks:** These tasks allow to create, copy, move, rename or delete files and directories on a file system. These tasks allow also to check whether a collection of remote or local files and/or directories exists.
- **Sync task:** This task allows to synchronise the content of a local or a remote source directory to a local or a remote destination directory. This task makes use of Microsoft Sync Framework 2.1.
- **Compression tasks:** These tasks allow to create a zip, a tar or a tar.gz from a collection of files.
- **MD5 task:** This task allows to generate MD5 sums of a collection of files.
- **FTP task:** This task allows to list, upload, download or delete files over FTP, FTPS (explicit/implicit) or SFTP. This task makes use of open source libraries written in C#.
- **HTTP task:** This task allows to downoad files over HTTP or HTTPS.
- **XML tasks:** These tasks allow to work with XML data. XSLT can be used along with XPath to generate XML documents. XSLT 1.0 and XSLT 2.0 are supported.
- **CSV tasks:** These tasks allow to work with CSV data. XML can be used along with XSLT to validate, compare and merge CSV data. The results of this can then be stored in CSV or XML format.
- **SQL task:** This task allows to execute SQL scripts. This task supports Microsoft Sql Server, Microsoft Access, Oracle, MySql, SQLite, PostGreSql and Teradata. This task can be used for bulk insert, for database updates, for database cleanup, for rebuilding indexes, for reorganizing indexes, for shrinking databases, for updating statistics, for transfering database data and so on.
- **WMI task:** This task allows to execute WMI queries. The results can be stored in XML format.
- **Image task:** This task allows to convert images to the following formats:** Bmp, Emf, Exif, Gif, Icon, Jpeg, Png, Tiff and Wmf.
- **Audio and video tasks:** These tasks allow to convert, cut or edit audio and video files through FFMEG or VLC. These tasks can also be used to perform custom operations such as generating images and thumbnails from video files.
- **Email task:** This task allows to send a collection of emails.
- **Twitter task:** This task allows to send a collection of tweets.
- **Process task:** This task allows to launch any process on the computer.
- **Wait task:** This task allows to wait for a specified duration of time.
- **Script tasks:** These tasks allows execute custom tasks written in C# or VB.

At this time, Wexflow only supports sequential execution of tasks but more complex scenarios like DoWhile, DoIf, parallel tasks execution and so on are in the todo list and are comming soon.

# Prerequisites

To use Wexflow, you'll need basic skills in:
- XML
- XPath
- XSL

To create a custom task, you'll need basic skills in:
- XML
- XPath
- XSL if necessary
- C# or VB

At this time, Wexflow only supports creating and editing workflows in XML. However, creating and editing workflows in design mode are in the todo list and are comming soon. Wexflow Designer aims to allow folks who are not familiar with XML to work with Wexflow so they can create and edit their workflows easily.

# How to install Wexflow

Wexflow can be installed on Windows XP, Windows server 2003 and higher. Wexflow supports .NET Framework 4.0 and higher.

To install Wexflow, proceed as follows:

1. Install Microsoft .NET Framework 4.0 or higher.

2. Install Microsoft Sync Framework 2.1 Synchronization Redistributables (Synchronization-v2.1-x86-ENU.msi available in Wexflow_setup.zip).

3. Install Microsoft Sync Framework 2.1 Provider Services Redistributables (ProviderServices-v2.1-x86-ENU.msi available in Wexflow_setup.zip)

4. Install WexflowSetup.exe (available in Wexflow_setup.zip):

![alt tag](https://aelassas.github.io/Wexflow/setup-1.PNG)

You can choose to create a desktop shortcut:

![alt tag](https://aelassas.github.io/Wexflow/setup-2.PNG)

Click on install to perform the installation:

![alt tag](https://aelassas.github.io/Wexflow/setup-3.PNG)

Finally, click on finish to finish the installation:

![alt tag](https://aelassas.github.io/Wexflow/setup-4.PNG)

The following menus are added in the start menu:

![alt tag](https://aelassas.github.io/Wexflow/wsm.png)

After Wexflow is installed a Windows Service named Wexflow is installed and starts automatically. To start Wexflow Manager, this Windows Service must be running. However, If you want to stop it you can do it from Windows Services console:

![alt tag](https://aelassas.github.io/Wexflow/ws.PNG)

The "Documentation" menu opens the documentation folder of Wexflow. The "Configuration" menu opens the configuration folder of Wexflow. The "Logs" menu opens the log file of the day.

# How to uninstall Wexflow
To uninstall Wexflow, simply click on "Uninstall" menu from "Windows Start menu > Wexflow".

Or go to "Configuration Panel > Add/remove programs" then select "Wexflow version 1.0.1" and click on uninstall:

![alt tag](https://aelassas.github.io/Wexflow/wu.PNG)

After Wexflow is uninstalled, the folders C:\Wexflow\ and C:\WexflowTesting\ are not deleted to prevent user defined workflows and testing scenarios from being deleted. However, If you do not need them you can delete them manually.

The log file C:\Program Files\Wexflow\Wexflow.log is also not deleted to keep track of the last operations done by Wexflow. However, If you do not need the logs you can delete the log files.

# How to use Wexflow

## General

After installing Wexflow, the folders C:\Wexflow\ and C:\WexflowTesting\ are created. The folder C:\Wexflow\ contains the following elements:

- **Wexflow.xml** which is the main configuration file of Wexflow engine. Its path can be configured from C:\Program Files\Wexflow\Wexflow.Clients.WindowsService.exe.config
- **Workflows/** which contains the workflows in XML format.
- **Temp/** which is the temporary foler of Wexflow.

The folder C:\WexflowTesting\ contains data of testing scenarios.

The logs are written in C:\Program Files\Wexflow\Wexflow.log. There is one log file per day. The old log files are saved in this format C:\Program Files\Wexflow\Wexflow.logyyyyMMdd.

Below the configuration file of a workflow:

```xml
<?xml version="1.0" encoding="utf-8" ?>
<!--
    This is the configuration file of a workflow. 
    A workflow is composed of:
      - An id which is an integer that must be unique.
      - A name which is a string that must be unique.
      - A description wich is a string.
      - A settings section which is composed of the following elements:
        - A launchType which is one of the following options:
          - startup: The workflow is launched when Wexflow engine starts.
          - trigger: The workflow is launched manually from the Wexflow manager.
          - periodic: The workflow is lauched periodically.
        - A period which is necessary for the periodic launchType. It is 
          a timeSpan in this format dd.hh:mm:ss. For example the period
          00.00:02:00 will launch the workflow every 2 minutes.
        - The enabled option which allows to enable or disable a workflow.
          The possible values are true or false.
      - A Tasks section which contains the tasks that will be executed by
        the workflow one after the other.
        - A Task is composed of:
          - An id which is an integer that must be unique.
          - A name wich is one of the options described in the tasks documentation.
          - A description which is a string.
          - The enable option which allows to enable or disable a task. The possible 
            values are true or false.
          - A collection of settings.
-->
<Workflow id="$int" name="$string" description="$string">
  <Settings>
    <Setting name="launchType" value="startup|trigger|periodic" />
    <Setting name="period" value="dd.hh:mm:ss" />
    <Setting name="enabled" value="true|false" />
  </Settings>
  <Tasks>
    <Task id="$int" name="$string" description="$string" enabled="true|false">
      <Setting name="$string" value="$string" />
      <Setting name="$string" value="$string" />
      <!-- You can add as many settings as you want. -->
    </Task>
    <Task id="$int" name="$string" description="$string" enabled="true|false">
      <Setting name="$string" value="$string" />
      <Setting name="$string" value="$string" />
    </Task>
    <!-- You can add as many tasks as you want. -->
  </Tasks>
</Workflow>
```

The name option of a Task must be one of the followings:
- **CsvToXml:** This task transforms a CSV file to an XML file. The format of the output XML file is described in the documentation of the task.
- **FilesCopier:** This task copies a collection of files to a destination folder. 
- **FilesLoader:** This task loads a collection of files located in folders or through the file option. 
- **FilesMover:** This task moves a collection of files to a destination folder.
- **FilesRemover:** This task deletes a collection of files.
- **Ftp:** This task allows to list, upload, download or delete files over FTP, FTPS (explicit/implicit) or SFTP. This task makes use of open source libraries written in C#.
- **ListEntities:** This task lists all the entities loaded by the workflow tasks in the logs. This task is useful for resolving issues.
- **ListFiles:** This task lists all the files loaded by the workflow tasks in the logs. This task is useful for resolving issues.
- **MailsSender:** This task sends a collection of emails from XML files. The format of the input XML files is described in the documentation of the task.
- **Md5:** This task generates MD5 sums of a collection of files and writes the results in an XML file. The format of the output XML file is described in the documentation of the task.
- **Mkdir:** This task creates a collection of folders.
- **ProcessLauncher:** This task launches a process. If the process generates a file as output It is possible to pass a collection of files to the task so that for each file an output file will be generated through the process. Read the documentation of the task for further informations.
- **Rmdir:** This task deletes a collection of folders.
- **Touch:** This task creates a collection of empty files.
- **Twitter:** This task sends a collection of tweets from XML files. The format of input XML files is described in the documentation of the task.
- **XmlToCsv:** This task transforms an XML file to a CSV file. The format of the input XML file is described in the documentation of the task.
- **Xslt:** This task transforms an XML file. It is possible to use XSLT 1.0 processor or XSLT 2.0 processor.
- **Zip:** This task creates a zip archive from a collection of files.
- **Tar:** This task creates a tar archive from a collection of files.
- **Tgz:** This task creates a tar.gz archive from a collection of files.
- **Sql:** This task executes a colletion of SQL script files or a simple SQL script through sql settings option. It supports Microsoft Sql Server, Microsoft Access, Oracle, MySql, SQLite, PostGreSql and Teradata.
- **Wmi:** This task executes a WMI query and outputs the results in an XML file. The format of the output XML file is described in the documentation of the task.
- **ImagesTransformer:** This task transforms a collection of image files to a specified format. The output format can be one of the followings: Bmp, Emf, Exif, Gif, Icon, Jpeg, Png, Tiff or Wmf.
- **Http:** This task allows to downoad files over HTTP or HTTPS.
- **Sync:** This task allows to synchronise the content of a local or remote source directory to a local or remote destination directory. This task makes use of Microsoft Sync Framework 2.1.
- **FilesRenamer:** This task allows to rename a collection of files on a file system. The Xslt task can be used along with the ListFiles task to create new file names. Check out the documentation of these tasks and the workflow sample Workflow_FilesRenamer.xml to see how this can be done.
- **Wait:** This task waits for a specified duration of time.
- **FilesExist:** This task checks whether a collection of files and/or directories exists.

To learn how to make your own workflows, you can check out the workflow samples availabe in C:\Wexflow\Workflows\ and read the tasks documentations available in the documentation folder C:\Program Files\Wexflow\Documentation.

If a new workflow is created in C:\Wexflow\Workflows\ or if an existing workflow is deleted or modified, you have to restart Wexflow Windows Service so that these modifications take effect.

To disable a workflow, you can set the enabled settings option of the workflow to false. If you want to make a workflow disappears from the list of the workflows loaded by Wexflow engine, you can create a directory named disabled within C:\Wexflow\Workflows\ and move that workflow to that directory then restart Wexflow Windows service.

## Wexflow Manager

![alt tag](https://aelassas.github.io/Wexflow/wm.PNG)

Wexflow Manager is a simple application that allows the user to do the following things:

- See all the workflows loaded by Wexflow Engine.
- See the status of the selected workflow (running, suspended or disabled).
- Start a workflow.
- Stop a workflow.
- Suspend a workflow.
- Resume a workflow.

To see what's going on in Wexflow, open the log file C:\Program Files\Wexflow\Wexflow.log in a text editor like [Notepad++](https://notepad-plus-plus.org/download/v7.3.1.html). Notepad ++ will update the log file as it fills up.

# Workflow samples

In this section, few workflow samples will be presented in order to make the end user familiar with Wexflow workflows synthax.

## Workflow 1

![alt tag](https://aelassas.github.io/Wexflow/Workflow_Invoices.png)

This workflow uploads invoices to an SFTP server, then waits for 2 days and then notifies the customers.

```xml
<Workflow id="99" name="Workflow_Invoices" description="Workflow_Invoices">
    <Settings>
        <Setting name="launchType" value="trigger" />
        <Setting name="enabled" value="true" />
    </Settings>
    <Tasks>
        <Task id="1" name="FilesLoader" description="Loading invioces" enabled="true">
            <Setting name="folder" value="C:\WexflowTesting\Invoices\" />
        </Task>
        <Task id="2" name="Ftp" description="Uploading invoices" enabled="true">
            <Setting name="protocol" value="sftp" /> <!-- ftp|ftps|sftp -->
            <Setting name="command" value="upload" /> <!-- list|upload|download|delete -->
            <Setting name="server" value="127.0.1" />
            <Setting name="port" value="21" />
            <Setting name="user" value="user" />
            <Setting name="password" value="password" />
            <Setting name="path" value="/" />
            <Setting name="selectFiles" value="1" />
        </Task>
        <Task id="3" name="Wait" description="Waiting for 2 days" enabled="true">
            <Setting name="duration" value="2.00:00:00" />
        </Task>
        <Task id="4" name="FilesLoader" description="Loading emails" enabled="true">
            <Setting name="file" value="C:\WexflowTesting\Emails\Invoices.xml" />
        </Task>
       <Task id="5" name="MailsSender" description="Notifying customers" enabled="true">
            <Setting name="selectFiles" value="4" />
            <Setting name="host" value="127.0.0.1" />
            <Setting name="port" value="587" />
            <Setting name="enableSsl" value="true" />
            <Setting name="user" value="user" />
            <Setting name="password" value="password" />
        </Task>
        <Task id="6" name="FilesMover" description="Moving invoices" enabled="true">
            <Setting name="selectFiles" value="1" />
            <Setting name="destFolder" value="C:\WexflowTesting\Invoices_sent\" />
        </Task>
    </Tasks>
</Workflow>
```

First of all, the FilesLoader task loads all the invoices located in the folder C:\WexflowTesting\Invoices\, then the Ftp task uploads them to the SFTP server, then the Wait task waits for 2 days, then the FilesLoader task loads the emails in XML format and then the MailsSender task sends the emails. Finally, the FilesMover task moves the invoices to the folder C:\WexflowTesting\Invoices_sent\.

## Workflow 2

![alt tag](https://aelassas.github.io/Wexflow/Workflow_FilesSender.png)

This workflow waits for files to arrive in C:\WexflowTesting\Watchfolder1\ and C:\WexflowTesting\Watchfolder2\ then uploads them to an FTP server then moves them to C:\WexflowTesting\Sent\ folder. This workflow starts every 2 minutes.

```xml
<Workflow id="6" name="Workflow_FilesSender" description="Workflow_FilesSender">
    <Settings>
        <Setting name="launchType" value="periodic" />
        <Setting name="period" value="00.00:02:00.00" />
        <Setting name="enabled" value="true" />
    </Settings>
    <Tasks>
        <Task id="1" name="FilesLoader" description="Loading files" enabled="true">
            <Setting name="folder" value="C:\WexflowTesting\Watchfolder1\" />
            <Setting name="folder" value="C:\WexflowTesting\Watchfolder2\" />
        </Task>
        <Task id="2" name="Ftp" description="Uploading files" enabled="true">
            <Setting name="protocol" value="ftp" /> <!-- ftp|ftps|sftp -->
            <Setting name="command" value="upload" /> <!-- list|upload|download|delete -->
            <Setting name="server" value="127.0.1" />
            <Setting name="port" value="21" />
            <Setting name="user" value="user" />
            <Setting name="password" value="password" />
            <Setting name="path" value="/" />
            <Setting name="selectFiles" value="1" />
        </Task>
        <Task id="3" name="FilesMover" description="Moving files to Sent folder" enabled="true">
            <Setting name="selectFiles" value="1" />
            <Setting name="destFolder" value="C:\WexflowTesting\Sent\" />
        </Task>
    </Tasks>
</Workflow>
```

First of all, the FilesLoader task loads all the files located in the folders C:\WexflowTesting\Watchfolder1\ and C:\WexflowTesting\Watchfolder2\ then the Ftp task loads the files and uploads them to the FTP server. Finally, the FilesMover task moves the files to the folder C:\WexflowTesting\Sent\.

## Workflow 3

![alt tag](https://aelassas.github.io/Wexflow/Workflow_ffmpeg.png)

This workflow transcodes the WAV files located in C:\WexflowTesting\WAV\ to MP3 format through FFMPEG and moves the transcoded files to C:\WexflowTesting\MP3\.

```xml
<Workflow id="12" name="Workflow_ffmpeg" description="Workflow_ffmpeg">
    <Settings>
        <Setting name="launchType" value="trigger" />
        <Setting name="enabled" value="true" />
    </Settings>
    <Tasks>
        <Task id="1" name="FilesLoader" description="Loading WAV files" enabled="true">
            <Setting name="folder" value="C:\WexflowTesting\WAV\" />
        </Task>
        <Task id="2" name="ProcessLauncher" description="WAV to MP3" enabled="true">
            <Setting name="selectFiles" value="1" />
            <!-- You need to install FFMPEG -->
            <Setting name="processPath" value="C:\Program Files\ffmpeg\bin\ffmpeg.exe" />
            <!-- variables: {$filePath},{$fileName},{$fileNameWithoutExtension}-->
            <Setting name="processCmd" value="-i {$filePath} -codec:a libmp3lame -qscale:a 2 {$output:$fileNameWithoutExtension.mp3}" /> 
            <Setting name="hideGui" value="true" />
            <Setting name="generatesFiles" value="true" /> 
        </Task>
        <Task id="3" name="FilesMover" description="Moving MP3 files from temp folder" enabled="true">
            <Setting name="selectFiles" value="2" />
            <Setting name="destFolder" value="C:\WexflowTesting\MP3\" />
        </Task>
    </Tasks>
</Workflow>
```

First of all, the FilesLoader task loads all the files located in the folder C:\WexflowTesting\WAV\ then the ProcessLauncher task launches FFMPEG process on every file by specifying the right command in order to create the MP3 file. Finally, the FilesMover task moves the MP3 files to the folder C:\WexflowTesting\MP3\.

## Workflow 4

![alt tag](https://aelassas.github.io/Wexflow/Workflow_vlc.png)

This workflow waits for WAV files to arrive in C:\WexflowTesting\WAV\ then transcodes them to MP3 files through VLC then uploads the MP3 files to an FTP server then moves the WAV files to C:\WexflowTesting\WAV_processed\. This workflow starts every 2 minutes.

```xml
<Workflow id="13" name="Workflow_vlc" description="Workflow_vlc">
    <Settings>
        <Setting name="launchType" value="periodic" />
        <Setting name="period" value="00.00:02:00.00" />
        <Setting name="enabled" value="true" />
    </Settings>
    <Tasks>
        <Task id="1" name="FilesLoader" description="Loading WAV files" enabled="true">
            <Setting name="folder" value="C:\WexflowTesting\WAV\" />
        </Task>
        <Task id="2" name="ProcessLauncher" description="WAV to MP3" enabled="true">
            <Setting name="selectFiles" value="1" />
            <!-- You need to install VLC-->
            <Setting name="processPath" value="C:\Program Files\VideoLAN\VLC\vlc.exe" />
            <!-- variables: {$filePath},{$fileName},{$fileNameWithoutExtension}-->
            <Setting name="processCmd" value="-I dummy {$filePath} :sout=#transcode{acodec=mpga}:std{dst={$output:$fileNameWithoutExtension.mp3},access=file} vlc://quit" />
            <Setting name="hideGui" value="true" />
            <Setting name="generatesFiles" value="true" />
        </Task>
        <Task id="3" name="Ftp" description="Uploading MP3 files" enabled="true">
            <Setting name="protocol" value="ftp" />
            <Setting name="command" value="upload" />
            <Setting name="server" value="127.0.1" />
            <Setting name="port" value="21" />
            <Setting name="user" value="user" />
            <Setting name="password" value="password" />
            <Setting name="path" value="/" />
            <Setting name="selectFiles" value="2" />
        </Task>
        <Task id="4" name="FilesMover" description="Moving WAV files" enabled="true">
            <Setting name="selectFiles" value="1" />
            <Setting name="destFolder" value="C:\WexflowTesting\WAV_processed\" />
        </Task>
    </Tasks>
</Workflow>
```

First of all, the FilesLoader task loads all the files located in the folder C:\WexflowTesting\WAV\ then the ProcessLauncher task launches VLC process on every file by specifying the right command in order to create the MP3 file. Then, the Ftp task loads the MP3 files generated by the ProcessLauncher task and then uploads them to the FTP server. Finally, the FilesMover task moves the processed WAV files to the folder C:\WexflowTesting\WAV_processed\.

## Workflow 5

![alt tag](https://aelassas.github.io/Wexflow/Workflow_Ftp_download_tag.png)

This workflow downloads specific files from an FTP server. This workflow starts by listing all the files located at the root folder of the server, then the specific files that will be downloaded are tagged through an XSLT (LisFiles.xslt), then the files are downloaded by the Ftp task through todo="toDownload" and from="app4" tags, then the downloaded files are moved to the folder C:\WexflowTesting\Ftp_download\.

```xml
<Workflow id="40" name="Workflow_Ftp_download_tag" description="Workflow_Ftp_download_tag">
    <Settings>
        <Setting name="launchType" value="trigger" /> <!-- startup|trigger|periodic -->
        <Setting name="enabled" value="true" /> <!-- true|false -->
    </Settings>
    <Tasks>
        <Task id="1" name="Ftp" description="Listing files (FTP)" enabled="true">
            <Setting name="command" value="list" />
            <Setting name="protocol" value="ftp" /> <!-- ftp|ftps|sftp -->
            <Setting name="server" value="127.0.1" />
            <Setting name="port" value="21" />
            <Setting name="user" value="user" />
            <Setting name="password" value="password" />
            <Setting name="path" value="/" />
        </Task>
        <Task id="2" name="ListFiles" description="Listing files" enabled="true">
        </Task>
        <Task id="3" name="Xslt" description="Renaming and tagging files" enabled="true">
            <Setting name="selectFiles" value="2" />
            <Setting name="xsltPath" value="C:\Wexflow\Xslt\ListFiles.xslt" />
            <Setting name="version" value="2.0" /> <!-- 1.0|2.0 -->
            <Setting name="removeWexflowProcessingNodes" value="false" />
        </Task>
        <Task id="4" name="Ftp" description="Downloading files" enabled="true">
            <Setting name="command" value="download" />
            <Setting name="protocol" value="ftp" /> <!-- ftp|ftps|sftp -->
            <Setting name="server" value="127.0.1" />
            <Setting name="port" value="21" />
            <Setting name="user" value="user" />
            <Setting name="password" value="password" />
            <Setting name="path" value="/" />
            <Setting name="selectFiles" todo="toDownload" from="app4" />
        </Task>
        <Task id="5" name="FilesMover" description="Moving files to Ftp_download" enabled="true">
            <Setting name="selectFiles" value="4" />
            <Setting name="destFolder" value="C:\WexflowTesting\Ftp_download\" />
            <Setting name="overwrite" value="true" />
        </Task>
    </Tasks>
</Workflow>
```

Roughly speaking, the Ftp task loads the list of files located at the root folder of the FTP server in the running instance of the workflow, then the ListFiles task outputs and XML file that contains all the files loaded then the Xslt task takes as input this XML and generates an XML wich contains a system node called WexflowProcessing wich contains the list of files to be tagged and/or renamed.

To understand how tagging and renaming files work, refer to the documentation of the ListFiles and Xslt tasks.

Below is the XSLT ListFiles.xslt used for tagging files:

```xml
<?xml version="1.0" encoding="utf-8"?>
<xsl:stylesheet version="1.0" xmlns:xsl="http://www.w3.org/1999/XSL/Transform">
  <xsl:output method="xml" indent="yes"/>

  <xsl:template match="/">
    <root>
      <WexflowProcessing>
        <xsl:for-each select="//WexflowProcessing/Workflow/Files//File">
          <xsl:choose>
            <xsl:when test="@name = 'file1.txt'">
              <File taskId="{@taskId}" name="{@name}" renameTo="file1_renamed.txt" 
                    todo="toRename" 
                    from="app1" />
            </xsl:when>
            <xsl:when test="@name = 'file2.txt'">
              <File taskId="{@taskId}" name="{@name}" renameTo="file2_renamed.txt" 
                    todo="toSend" 
                    from="app2" />
            </xsl:when>
            <xsl:when test="@name = 'file3.txt'">
              <File taskId="{@taskId}" name="{@name}" renameTo="file3_renamed.txt" 
                    todo="toDownload" 
                    from="app3" />
            </xsl:when>
            <xsl:when test="@name = 'file4.txt'">
              <File taskId="{@taskId}" name="{@name}" renameTo="file4_renamed.txt"
                    todo="toDownload" 
                    from="app4" />
            </xsl:when>
          </xsl:choose>
        </xsl:for-each>
      </WexflowProcessing>
    </root>
  </xsl:template>
</xsl:stylesheet>
```

These are simple and basic workflows to give an idea on how to make your own workflows. However, if you have multiple systems, applications and automations involved in a workflow, the workflow could be very interesting.

# How to create a custom task

To create a custom task MyTask for example you will need to proceed as follows:

1. Create a class library project in Visual Studio and name it Wexflow.Tasks.MyTask.
2. Reference the assemblies Wexflow.Core.dll and log4net.dll.These assemblies are located in the installation folder of Wexflow C:\Program Files\Wexflow\.
3. Create a public class MyTask that implements the abstract class Wexflow.Core.Task.

Wexflow.Tasks.MyTask code should look like as follows:

```cs
public class MyTask : Wexflow.Core.Task
{
    public MyTask(XElement xe, Workflow wf) : base(xe, wf)
    {
        // Task settings goes here
    }

    public override void Run()
    {
        try
        {
            // Task logic goes here
        }
        catch (ThreadAbortException)
        {
            throw;
        }
    }
}
```

To retrieve settings, you can use the following methods:

```cs
string settingValue = this.GetSetting("settingName");
string settingValue = this.GetSetting("settingName", defaultValue);
string[] settingValues = this.GetSettings("settingName");
```

To select the files loaded by the running instance of a workflow through the selectFiles settings option, you can do it as follows:

```cs
FileInf[] files = this.SelectFiles();
```

To select entities loaded by the running instance of a workflow through the selectEntities settings option, you can do it as follows:

```cs
Entity[] entities = this.SelectEntities();
```

The Entity class could be very useful when working with custom tasks that manipulate objects from a database or Web Services for example.

To load a file within a task, you can do it as follows:

```cs
this.Files.Add(new FileInf(path, this.Id));
```

To load an entity within a task, you can do it as follows:

```cs
this.Entities.Add(myEntity);
```

Finally if you finished coding your custom task, compile the class library project and copy the assembly Wexflow.Tasks.MyTask.dll in C:\Program Files\Wexflow\. Your custom task is then ready to be used as follows:

```xml
<Task id="$int" name="MyTask" description="My task description" enabled="true">
    <Setting name="settingName" value="settingValue" />
</Task>
```

That's it. That's all the things you need to know to start coding your own custom tasks.

# How to debug Wexflow

How to debug Wexflow
To debug Wexflow, proceed as follows:

- Install Microsoft .NET Framework 4.0 or higher.
- Install Microsoft Sync Framework 2.1 SDK. You can download it from [here](https://www.microsoft.com/en-us/download/details.aspx?id=23217).
- Install Visual Studio 2010 or higher.
- Copy the folders "Wexflow" and "WexflowTesting" in C:\. You can download them from [here](https://aelassas.github.io/Wexflow/Wexflow.zip).

## Wexflow Windows Service

To debug Wexflow Windows Service (Wexflow.Clients.WindowsService project), add "debug" command line argument in "Propject settings > Debug > Startup options":

![alt tag](https://aelassas.github.io/Wexflow/wwsd.png)

## Wexflow Manager

To debug Wexflow Manager (Wexflow.Clients.Manager project), add "debug" command line argument in "Propject settings > Debug > Startup options":

![alt tag](https://aelassas.github.io/Wexflow/wmd.png)

# Libraries used by Wexflow

Here is the list of the libraries used by Wexflow:

- [FluentFTP](https://github.com/hgupta9/FluentFTP): An FTP client supporting FTP and FTPS(exmplicit/implicit) written in C# and under MIT license.
- [SSH.NET](https://github.com/sshnet/SSH.NET): An SSH library for .NET written in C# and under MIT license.
- [SharpZipLib](https://github.com/icsharpcode/SharpZipLib): A Zip, GZip, Tar and BZip2 library written in C# and under MIT license.
- [Saxon-HE](http://saxon.sourceforge.net/): An XSLT and XQuery Processor that provides implementations of XSLT (2.0), XQuery (1.0, 3.0, and 3.1), and XPath (2.0, 3.0, and 3.1) at the basic level of conformance defined by W3C. It's an open source library available under the Mozilla Public License version 1.0.
- [log4net](https://logging.apache.org/log4net/): A port of the famous Apache log4j framework to the Microsoft .NET runtime. It's under the Apache license version 2.0.
- [TweetSharp](https://www.nuget.org/packages/TweetSharp/): A fast and clean wrapper around the Twitter AP written in C#.
- [Microsoft Sync Framework 2.1](https://msdn.microsoft.com/en-us/library/mt490616.aspx): A data synchronization platform that allows to synchronize data across multiple data stores.
- [Json.NET](https://github.com/JamesNK/Newtonsoft.Json): A high-performance JSON framework for .NET written in C# and under MIT license.
- [Hammock](https://www.nuget.org/packages/Hammock): an HTTP library that simplifies consuming and wrapping RESTful services.
- [Mono.Security](https://www.nuget.org/packages/Mono.Security/): A library that provides the missing pieces to .NET security.
- [Oracle Data Access Components (ODAC)](http://www.oracle.com/technetwork/topics/dotnet/utilsoft-086879.html): Oracle database client for .NET.
- [MySQL Connector/Net](https://dev.mysql.com/downloads/connector/net/1.0.html): A fully-managed ADO.NET driver for MySQL.
- [System.Data.SQLite](https://system.data.sqlite.org/): An ADO.NET provider for SQLite.
- [Npgsql](http://www.npgsql.org/): An open source ADO.NET Data Provider for PostgreSQL written in C# and under the PostgreSQL License, a liberal OSI-approved open source license.
- [.NET Data Provider for Teradata](http://downloads.teradata.com/download/connectivity/net-data-provider-for-teradata): An ADO.NET provider for Teradata.

# Todo list
- **Wexflow Engine:** Add XSD validation of the workflow files before loading them.
- **Tasks execution graph:** Improve the tasks execution graph by allowing parallel execution of tasks, by provinding the ability to alter the execution flow of the tasks and by providing the ability to add DoIf, DoWhile, OnSuccess, OnWarning and OnError in the execution graph.
- **Linux:** Update Wexflow to work on Linux (Mono) and create a setup project for Linux.
- **Wexflow Manager:** Make the workflow status of the visible workflows live and highlight the workflows who are running in green.
- **Workflow jobs:** Allow parallel execution of the jobs of a workflow.
- **Wexflow Editor:** Add a tab in Wexflow Manager from wich the end user can view all the workflow files and from wich a workflow file can be edited, created or deleted. Wexflow Editor should handle XML synthax highlighting (FastColoredTextBox shoud do the job), opening multiple XML files in tabs like in Notepad++ and saving multiple XML files at the same time.
- **Wexflow Designer:** Add a tab in Wexflow Manager from wich the end user can view all the workflows and from wich a workflow can be edited, created or deleted in design mode through a user friendly UI that allows to view workflow tasks in boxes, to view and edit task settings in a panel located in the left and to create or delete a task. Wexflow Designer should handle Drag and Drop if possible. Wexflow Designer should allow users who are not familiar with XML to work with Wexflow.
- **Wexflow Web Manager:** Create a JavaScript library that provides HTML5 controls that allow to view the workflows by highlighting the workflows who are running, manage workflows (start a workflow, stop a workflow, suspend a workflow and resume a workflow), edit workflows (create a workflow, modify a workflow and delete a workflow). This library should provide user friendly functionalities such as Drag and Drop. The JavaScript library aims to allow Wexflow to be integrated in ASP.NET, PHP, Ruby on Rails, Python, HTML5 websites and so on. This library should allow users who do not know XML to work with Wexflow. Also, create a Web Manager in HTML5/CSS3 that makes use of this JavaScript library.
- **Wexflow Android Manager:** Create a Wexflow Manager for Android.
- **YouTube task:** Create a task that allows to upload, edit and delete videos on YouTube. This task should use YouTube Data API client library for .NET.

# History

- 5 Jan 2017:
  - [Released version 1.0](https://github.com/aelassas/Wexflow/releases/tag/v1.0).
- 9 Jan 2017: 
  - [Released version 1.0.1](https://github.com/aelassas/Wexflow/releases/tag/v1.0.1).
  - Created Wexflow Windows Service.
  - Created Tar, Tgz and Sql tasks.
  - Updated Wexflow Manager.
  - Fixed some bugs.
- 16 Jan 2017:
  - [Released version 1.0.2](https://github.com/aelassas/Wexflow/releases/tag/v1.0.2).
  - Created Wmi and ImagesTransformer tasks.
  - Updated Wexflow Manager.
- 23 Jan 2017:
  - [Released version 1.0.3](https://github.com/aelassas/Wexflow/releases/tag/v1.0.3).
  - Created Http, Sync, FilesRenamer, FilesExist and Wait tasks.
  - Created file tags functionality.
  - Added list, download and delete commands to Ftp task (FTP/FTPS(explicit/implicit)/SFTP).
  - Added retryCount and retryTimeout setting options to Ftp task.
  - Updated Wexflow manager.
  - Updated Wexflow engine.
  - Fixed some bugs.
  - Updated setup file.
  - Updated README.md.

# More informations
More informations about Wexflow can be found on [CodeProject](https://www.codeproject.com/Articles/1164009/Wexflow-Open-source-workflow-engine-in-Csharp).

# License
MIT.
