security_dlp_file_patterns - DLP File Pattern Resource
++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. versionadded:: 1.0.0

.. contents::
   :local:
   :depth: 1

Synopsis
--------
DLP File Pattern Resource.

Use API "/resource-api/v2/security/dlp-file-patterns".

Requirements
------------

The below requirements are needed on the host that executes this module.

- ansible>=2.17.0


Parameters
----------
.. raw:: html

 <ul>
 <li><span class="li-head">state</span> The state of the module. "present" means create or update the resource, "absent" means delete the resource.<span class="li-normal">type: str</span><span class="li-normal">choices: ['present', 'absent']</span><span class="li-normal">default: present</span></li>
 <li><span class="li-head">force_method</span> Specify this option to force the method to use to interact with the resource.<span class="li-normal">type: str</span><span class="li-normal">choices: ['none', 'get', 'post', 'put', 'delete']</span><span class="li-normal">default: none</span></li>
 <li><span class="li-head">bypass_validation</span> Bypass validation of the module.<span class="li-normal">type: bool</span><span class="li-normal">default: False</span></li>
 <li><span class="li-head">params</span> The parameters of the module.<span class="li-required">[Required]</span><span class="li-normal">type: dict</span> <ul class="ul-self"> <li><span class="li-head">primaryKey</span> <span class="li-required">[Required]</span><span class="li-normal">type: str</span></li>
 <li><span class="li-head">tag</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">entries</span> <span class="li-normal">type: list</span><span class="li-normal">elements: dict</span> <ul class="ul-self"> <li><span class="li-head">pattern</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">filterType</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['pattern', 'type']</span></li>
 <li><span class="li-head">fileType</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['.net', '7z', 'activemime', 'arj', 'aspack', 'avi', 'base64', 'bat', 'binhex', 'bmp', 'bzip', 'bzip2', 'cab', 'chm', 'class', 'cod', 'crx', 'dmg', 'elf', 'exe', 'flac', 'fsg', 'gif', 'gzip', 'hibun', 'hlp', 'hta', 'html', 'iso', 'jad', 'javascript', 'jpeg', 'lzh', 'mach-o', 'mime', 'mov', 'mp3', 'mpeg', 'msi', 'msoffice', 'msofficex', 'pdf', 'petite', 'png', 'rar', 'rm', 'sis', 'tar', 'tiff', 'torrent', 'unknown', 'upx', 'uue', 'wav', 'wma', 'xar', 'xz', 'zip']</span></li>
 </ul></li>
 </ul></li>
 </ul>



Examples
-------------

.. code-block:: yaml

  
  


Return Values
-------------
.. raw:: html

 <ul>
 <li><span class="li-head">http_code</span> <span class="li-normal">type: int</span><span class="li-normal">returned: always</span></li>
 <li><span class="li-head">response</span> <span class="li-normal">type: raw</span><span class="li-normal">returned: always</span></li>
 </ul>


Authors
-------

- Xinwei Du (@dux-fortinet)

