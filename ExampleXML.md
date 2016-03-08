# Introduction #

Just a simple example XML file. Definitely not pretty.

![http://img523.imageshack.us/img523/4152/wonkypreview3.png](http://img523.imageshack.us/img523/4152/wonkypreview3.png)


# Details #
```
<?xml version="1.0" encoding="utf-8"?>
<!--
		Wonky config 0.001 ALPHA by ikex <aktowns@gmail.com>
		Still alot more work to be done, but so far this contains a full WMI implementation
		i would like to add alot more helper commands (IE checkfill)
		Maybe some conversion commands from bytes to kbytes and etc
		but all in good time :)
-->
<WonkyConfig xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
	<Height>500</Height>
	<Width>700</Width>
	<LocationX>300</LocationX>
	<LocationY>300</LocationY>
	<DefaultFont>Segoe UI</DefaultFont>
	<DefaultFontSize>12</DefaultFontSize>
    <DefaultFontColour>AntiqueWhite</DefaultFontColour>
	<Sections>testsection</Sections>
	<RefreshRate>5000</RefreshRate> <!-- Milliseconds -->
	<WMIRefreshRate>60000</WMIRefreshRate> <!-- Set it too low and things tend to get funky ;) [ALWAYS KEEP ABOVE RefreshRate]-->
  <Blocks>
	<Block x="0" y="0" w="24" h="24" line="{IMAGE.'Win.png'}" />
	<Block x="26" y="0" line="{WMI.OperatingSystem.Caption}" />
	<Block x="0" y="25" FontSize="8" line="OS:" />
	<Block x="50" y="25" FontSize="8" line="Arch: {WMI.OperatingSystem.OSArchitecture} | Version: {WMI.OperatingSystem.Version} | Hostname: {WMI.Processor.SystemName}" />
	<Block x="0" y="45" FontSize="8" line="CPU:" />
	<Block x="50" y="43" FontSize="8" line="{WMI.Processor.Name}" />
	<Block x="50" y="53" FontSize="8" line="Speed: {WMI.Processor.MaxClockSpeed}mhz (FSB:{WMI.Processor.ExtClock}) | Cores: {WMI.Processor.NumberOfCores} | L2Cache: {WMI.Processor.L2CacheSize}kb" />
	<Block x="0" y="70" FontSize="8" line="Ram:" />
	<Block x="50" y="67" FontSize="8" line="Free/Total: {CONV.BKB.WMI.OperatingSystem.FreePhysicalMemory}MB/{CONV.BKB.WMI.OperatingSystem.TotalVisibleMemorySize}MB" />
	<Block x="0" y="100" FontSize="8" line="HDDs:" />
	
	<Block x="0" y="125" FontSize="8" line="Net:" />
	<Block x="50" y="123" FontSize="8" line="{WMI.NetworkAdapter.Name:13}" />
	<Block x="50" y="133" FontSize="8" line="Speed: {CONV.BMB.WMI.NetworkAdapter.Speed:13}Mbps | MAC: {WMI.NetworkAdapter.MACAddress:13}" />
	<Block x="50" y="143" FontSize="8" line="ipv4: {WMI.NetworkAdapterConfiguration.IPAddress:13} | ipv6: {WMI.NetworkAdapterConfiguration.IPAddress:13:1}" />
	<Block x="50" y="153" FontSize="8" line="" />
	<!--<Block x="50" y="125" FontSize="8" line="External IP: {EXEC.'cscript.exe ExternalIP.vbs //Nologo'}" />-->
  </Blocks>
</WonkyConfig>
```