正则验证规则参数
-----
```js
$.validateRegular = {
	//仅数字
	OnlyNumber: /^[\d]+$/,
	//仅中文
	OnlyChinese: /^[\u4e00-\ufa29]+$/,
	//非中文
	NotChinese: /^[^\u4E00-\u9FA5\uF900-\uFA2D\uFF00-\uFFEF]+$/,
	//电话号码验证(如: +861383838438 1383838438 0576xxxxxxxx 0576-xxxxxxxx 0576-xxxxxxxx-010 400-800-8888 10086)
	Tel: /(^([+]{1}[\d]{2})?[1]\d{10}$)|(^[1]\d{10}$)|(^\d{7,8}$)|(^((\d{3}|\d{4}))?-?\d{7,8}$)|(^((\d{3}|\d{4}))?-?\d{7,8}(-(\d{2}|\d{3}|\d{4}))?$)|(^\d{3}-\d{3}-\d{4}$)|(^\d{5}$)|(^\d{3}-\d{3}-\d{8}$)/,
	//手机号码验证(如:+861383838438 1383838438)
	Mobile: /(^([+]{1}[\d]{2})?[1]\d{10}$)|(^[1]\d{10}$)/,
	//Email地址验证
	Email: /^[\w\-\.]+@[\w\-\.]+(\.\w+)+$/,
	//邮政编码验证
	PostCode: /^[0-9]{6}$/,
	//传真验证
	Fax: /^[+]{0,1}(\d){1,3}[ ]?([-]?((\d)|[ ]){1,12})+$/,
	//QQ号格式验证
	QQ: /^[1-9][0-9]{4,9}$/,
	//IP地址验证
	IP: /^(\d{1,3}.){3}(\d{1,3})$/,
	//图片验证
	Img: new RegExp("\.(?:jpg|jpeg|gif|png|ai|pdg|bmp|ico|tif|pcx|dxf|cdr)$$", "i"),
	//Url验证
	Url: /^[^:.\/?%&=“”,@!~\-\+\(\)\*\$\#`\u0022\u0027]([http:\/\/]{6})?((([w]{3}\.)?([\w-]+[\.][\w-]+)+)|([\d]{1,3}[\.]{1}[\d]{1,3}[\.]{1}[\d]{1,3}[\.]{1}[\d]{1,3})|([\w]+))([:][\d]+)?(\/[\w- ;.\/?%&=_#\u4E00-\u9FA5]+)*(\.[\w-\u4E00-\u9FA5]+)*([?\w=%&\|\u4E00-\u9FA5]+)?$/,
	//包含http的url验证
	UrlProtocol: /^[^:.\/?%&=“”,@!~\-\+\(\)\*\$\#`\u0022\u0027][http:\/\/]{6}((([w]{3}\.)?([\w-]+[\.][\w-]+)+)|([\d]{1,3}[\.]{1}[\d]{1,3}[\.]{1}[\d]{1,3}[\.]{1}[\d]{1,3})|([\w]+))([:][\d]+)?(\/[\w- ;.\/?%&=_#\u4E00-\u9FA5]+)*(\.[\w-\u4E00-\u9FA5]+)*([?\w=%&\|\u4E00-\u9FA5]+)?$/,
	//Guid验证
	Guid: /^(\{{0,1}([0-9a-fA-F]){8}-([0-9a-fA-F]){4}-([0-9a-fA-F]){4}-([0-9a-fA-F]){4}-([0-9a-fA-F]){12}\}{0,1})$/,
	//是否空Guid
	IsEmptyGuid: /^(\{{0,1}[0]{8}-([0]{4}-){3}[0]{12}\}{0,1})$/,
	//判断Json字符串
	IsJson: /^\{(.+:.+,*){1,}\}$/
};
```