
.PHONY: brun
brun:
	docker build -t wasm-test-server -f docker/Dockerfile .
	docker run -d --rm -p 80:80 wasm-test-server
