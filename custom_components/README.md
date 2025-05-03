# Custom Components

Please refer to [components-custom-components](https://docs.langflow.org/components-custom-components) for more information.

### Setup custom components in docker compose file

- Add environment variable `LANGFLOW_COMPONENTS_PATH` in docker compose file with `/app/custom_components/`.
- Mount `/your/custom/components/path` with `LANGFLOW_COMPONENTS_PATH`

```
...
    environment:
      ...
      - LANGFLOW_COMPONENTS_PATH=/app/custom_components/
    volumes:
      ...
      - /your/custom/components/path:/app/custom_components/
```

By default, Langflow looks for custom components in the langflow/components directory.

If you're creating custom components in a different location using the LANGFLOW_COMPONENTS_PATH LANGFLOW_COMPONENTS_PATH environment variable, components must be organized in a specific directory structure to be properly loaded and displayed in the UI:

```
/your/custom/components/path/ # Base directory (set by LANGFLOW_COMPONENTS_PATH)
└── category_name/ # Required category subfolder (determines menu name)
└── custom_component.py # Component file
```

Components must be placed inside category folders, not directly in the base directory. The category folder name determines where the component appears in the UI menu.

For example, to add a component to the Helpers menu, place it in a helpers subfolder:

```
/app/custom_components/ # LANGFLOW_COMPONENTS_PATH
└── helpers/ # Shows up as "Helpers" menu
└── custom_component.py # Your component
```

You can have multiple category folders to organize components into different menus:

```
/app/custom_components/
├── helpers/
│ └── helper_component.py
└── tools/
└── tool_component.py
```

This folder structure is required for Langflow to properly discover and load your custom components. Components placed directly in the base directory will not be loaded.

```
/app/custom_components/ # LANGFLOW_COMPONENTS_PATH
└── custom_component.py # Won't be loaded - missing category folder!
```
