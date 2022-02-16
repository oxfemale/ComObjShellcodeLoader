# ComObjShellcodeLoader
ComObject Shellcode Loader with fake return address.

You'll need to Export DllGetClassObject.

writed on .Net


COM_plete : Load shellcode by faking a return offfset.

HRESULT DllGetClassObject(
  [in]  REFCLSID rclsid,
  [in]  REFIID   riid,
  [out] LPVOID   *ppv , <--- Offset to shellcode here :)
);



run:
c:\Windows\Microsoft.NET\Framework\v4.0.30319\csc.exe /target:library com_plete.cs

c:\Program Files (x86)\Microsoft SDKs\Windows\v10.0A\bin\NETFX 4.8 Tools\ildasm.exe" /out:com_plete.il com_plete.dll c:\Windows\Microsoft.NET\Framework\v4.0.30319\ilasm.exe /DLL /x64 com_plete.il
