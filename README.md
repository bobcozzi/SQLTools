# SQLTools
SQL Tools - High performance SQL functions for IBM i and RPG IV
<p>SQL Tools provides SQL Table Function (UDTF) wrappers for most IBM i APIs as well as providing additional capabilities, such as financial functions, CSV support and IFS read/write capabilities.</p>
<p>SQL Tools may be installed and run on IBM i Version 7.2 and later without changes. That is if you have V7R2 and V7R5 partitions, you can use the exact same SQL Tools functions on both without syntax issues or feature restrictions.</p>
<p>SQL Tools is a licensed program product (2COZ-ST3) under a one-time-charge (OTC) model.</p>
<p>A license key for your current system is available for a one-time-charge (OTC) of $595 for all partitions on one physical system. It is a perpetual license.</p> 
<p>To receive support, email Bob Cozzi at the link below or connect over on LinkedIn.</p>
<h3>Download and Install</h3>
<p>To download SQL Tools for IBM i, click on the link below that best matches your current IBM i version.</p>
<p>SQL Tools for IBM i V7R2 only: <a href="https://www.dropbox.com/scl/fi/ll3b1t83v8g3wmfaudx8j/SQLTOOLS72.savf?rlkey=mki43jlcv6hykus11q1z0cvq5&dl=1">Download V7R2 save file image</a></p>
<p>SQL Tools for IBM i V7R3 and later: <a href="https://www.dropbox.com/scl/fi/71wj67rv2vr2ruzxbczan/SQLTOOLS.savf?rlkey=f76v5pmaottk7l4f6vpopan0x&dl=1">Download V7R3+ save file image</a></p>
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
