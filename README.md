# terraform-rd
parse module
https://github.com/hashicorp/hcl

The following code can take a (.tf) file and output the JSON.
```
FileContent, err := ioutil.ReadFile("new.tf") // just pass the file name
	if err != nil {
		fmt.Print(err)
	}
	var out interface{}
	FileContentString := string(FileContent) // convert content to a 'string'
	err = hcl.Decode(&out, FileContentString)
	fmt.Println(out)

	outData, err := json.Marshal(out)
	if err != nil {
		fmt.Println(err.Error())
		return
	}
	jsonStr := string(outData)
	fmt.Println("The JSON data is:")
	fmt.Println(jsonStr) 
```

# also see
https://github.com/hashicorp/terraform-config-inspect