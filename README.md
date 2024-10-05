# SQLTools
SQL Tools - High performance SQL functions for IBM i and RPG IV
<h2>SQL Tools v3.4 is now a no-charge licensed program</h2>
<p>Bob Cozzi IBM i SQL functions library, <b>SQLTOOLS</b> is now free to use by all IBM i customers. For updates visit this github page. For support, use the github forums here or go over to LinkedIn.com/in/BobCozzi and tag Bob Cozzi in your message.</p>
  <p>Existing customers can update to V3.4 at no charge anytime. Just download it from the Release link on the right side of this page.</p>
<p>SQL Tools provides SQL Table Function (UDTF) wrappers for most IBM i APIs as well as providing additional capabilities, such as financial functions, CSV support and IFS read/write capabilities.</p>
<p>SQL Tools may be installed and run on IBM i Version 7.2 and later without changes. That is if you have V7R2 and V7R5 partitions, you can use the exact same SQL Tools functions on both without syntax issues or feature restrictions.</p>
<h3>Download and Install</h3>
<p>To download SQL Tools for IBM i, click on the Release link on the right-side of this page. Then select the appropriate save file. Most users on IBM i V7R3 and later should download and install the SQLTOOLS.SAVF, while those on V7R2 should use the SQLTOOLS72.SAVF for their system.</p>
<p>Once you have downloaded the save file to your PC, upload it to the IBM i server using binary mode FTP or similar. Normally you should create a save file object on the IBM i server in QGPL and upload the PC .SAVF to that host file.
IBM i allows you to create a save file using the CRTSAVF CL command.</p>
<pre>CRTSAVF QGPL/SQLTOOLS</pre>
If the save file already exists, you should clear it before performing the FTP upload.
<pre>CLRSAVF QGPL/SQLTOOLS</pre>
<p>If the SAVF does not exist, FTP BINARY upload will automatically create it correctly if and only if the PC file name SQLTOOLS.SAVF or SQLTOOLS72.SAVF contains the <i>.SAVF</i> suffix.</p>
<h4>Installation</h4>
<p>To install SQL Tools, the RSTLICPGM (Restore Licensed Program) CL command is used. If a prior version of SQL Tools is already installed on your system, you need to remove it first before installing the latest release.</p>
<h5>Removing a pior SQL Tools installation</h5>
<p>Determine which version is installed. Use the GO LICPGM CL command to list all installed licensed programs</p>
<pre>GO LICPGM</pre>
<p>Selection option 10=Display and scroll down until you see licensed program 2COZ-STn where n is 1, 2, or 3</p>
<p>If you locate a prior installation, remove it using the DLTLICPGM CL command as follows:</p>
<pre>DLTLICPGM 2COZST3</pre>
<p>Be sure to replace the trailing '3' with the version you currently have installed.</p>
<h5>Install SQL Tools</h5>
<p>To install SQL Tools, use the RSTLICPGM CL command</p>
<pre>RSTLICPGM 2COZST3 *SAVF SAVF(QGPL/SQLTOOLS)</pre>
<p>If you are installing into an IBM i V7R2 partition, then use the save file named QGPL/SQLTOOLS72 on the RSTLICPGM command.</p>
<p>I also have a free CL command named <a href="https://github.com/bobcozzi/WRKOBJSQL">WRKOBJSQL (Work with SQL Objects)</a> that displays a list of the installed SQL objects in the specified library. NOTE: This command 
was previously named <i>WRKFUNC</i> and was included in the SQL iQuery package.</p>
<p>You can use:</p>
<pre>WRKOBJSQL SQLTOOLS</pre><p>to view the available functions, stored procedures and views that were installed by SQL Tools.</p>
