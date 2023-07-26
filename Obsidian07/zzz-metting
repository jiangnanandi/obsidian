<%* 
let input = await tp.system.prompt("输入会议标题：")
let templateName = tp.file.find_tfile("Metting-work")
let today = tp.date.now("YYYY-MM-DD")
let titleName = today+" - " + input
-%>
[[<% (await tp.file.create_new(templateName, titleName , false)).basename %>]]