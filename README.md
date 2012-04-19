flex-ui-generator
=================

Generic flex application to dynamically generate UI on the fly using XML metadata


Browser based Flex 3 application, which can generate Flex UI on-the-fly based on an XML layout definition file, it also 
support data binding, 

----- Sample XML layout --------

<?xml version="1.0" encoding="UTF-8"?>
<Application defaultPage="01" title="Test Applicaton" width="200" height="300" 
  xmlns:style="styles" xmlns:data="data" xmlns:module="module">
	<Modules>
		<Module id="FeedbackForm" url="modules/FeedbackFormModule.swf"/>
	</Modules>
	<Views>
		<View id="01">
			<Box direction="vertical" width="600" height="300"
				style:backgroundColor="silver" style:paddingLeft="10" style:paddingTop="10">
				
				<Box direction="horizontal" style:backgroundColor="#FFFFFF">
					<Button label="click 01"/>
					<Button label="click 02"/>
					<Button label="{combo02.selectedItem.title}"/>
				</Box>
				
				<Box direction="horizontal">
					<ComboBox  id="combo02" data:source="d01::/careerpathmetadata/functions/function" labelField="title"/>
					<Label text="This is text"/>	
					<TextInput text="This is text input"/>
				</Box>
				
				<TextInput text="01" style:backgroundColor="yellow"/>
				
				<module:FeedbackForm/>
			</Box>
		</View>
	</Views>
	<Data>
		<datasource id="d01" source="data/cp/data.xml"/>
	</Data>
</Application>