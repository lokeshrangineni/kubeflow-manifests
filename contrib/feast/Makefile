
feast/registry-server: clean
	cd feast/base && helm template feast-registry-server feast-charts/feast-feature-server \
                   --set feast_mode=registry \
                   --set feature_store_yaml_base64=$(shell cat feature_store_sample.yaml | base64 | tr -d '\n') \
                   --version 0.40.1 > resources.yaml

feast/online-server: clean
	cd feast/base && helm template feast-online-server feast-charts/feast-feature-server \
                   --set feast_mode=online \
                   --set feature_store_yaml_base64=$(shell cat feature_store_sample.yaml | base64 | tr -d '\n') \
                   --version 0.40.1 > resources.yaml

feast/offline-server: clean
	cd feast/base && helm template feast-offline-server feast-charts/feast-feature-server \
                   --set feast_mode=offline \
                   --set feature_store_yaml_base64=$(shell cat feature_store_sample.yaml | base64 | tr -d '\n') \
                   --version 0.40.1 > resources.yaml

feast/ui-server: clean
	cd feast/base && helm template feast-ui-server feast-charts/feast-feature-server \
                   --set feast_mode=ui \
                   --set feature_store_yaml_base64=$(shell cat feature_store_sample.yaml | base64 | tr -d '\n') \
                   --version 0.40.1 > resources.yaml

.PHONY:clean-kustomize
clean:
	rm -rf feast/base/resources.yaml