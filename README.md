# slcli-example-yaml-configs

Collection of SystemLink systems, assets, and test results defined in YAML files for installing examples with `slcli`.

## Prerequisites

- Install [SystemLink CLI](https://cli.systemlink.dev/).
- Connect `slcli` to a SystemLink server.

## Create and install an example

1. **Create a base YAML configuration.**
	Use it to outline your system and include an example of a location, product, asset setup, test result, and other relevant data. See the [two-cell base configuration](example-cca-thermocycle-test-data/base_config_2_cells.yaml).

	For more examples, see the [`slcli` examples](https://github.com/ni-kismet/systemlink-cli/tree/main/slcli/examples).

2. **Create an AI prompt describing your scenario.**
	Reference the base configuration and be specific: this is where you tell the story of your demo. See the [sample prompt](example-cca-thermocycle-test-data/sample_prompt.md).

3. **Use AI to create your new YAML configuration.**

4. **Install the configuration on the server with `slcli`.**
	Run a dry run first with `--dry-run` to find issues. Data ingestion may take a while, depending on the amount of data.

	```powershell
	slcli example install -w ADG --file "C:\git\slcli-example-yaml-configs\example-cca-thermocycle-test-data\config_800_duts.yaml"
	```

## Optional: Delete an example

Use `slcli` to remove the configuration from the server. The YAML tags everything it creates, allowing `slcli` to remove all data from the configuration with one command:

```powershell
slcli example delete -w ADG --file "C:\git\slcli-example-yaml-configs\example-cca-thermocycle-test-data\config_800_duts.yaml"
```
